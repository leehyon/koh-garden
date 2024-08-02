---
title: "Git FAQ"
date: 2024-07-10
tags:
  - faq
  - git
---

This section provides answers to commonly asked questions about Git.

## Change the most recent unpushed commit

1. Use the `git commit --amend` command.

2. Alternatively, you can directly set the new message with: `git commit --amend -m "Your new commit message"`

## Setup multiple git identities

> [Git config with multiple identities and multiple repositories](https://gist.github.com/bgauduch/06a8c4ec2fec8fef6354afe94358c89e)

## Git merge

`git merge`

By default, Git will try to perform a "fast-forward" merge if possible. A fast-forward merge simply moves the source branch reference forward to the target branch's latest commit, which maintains a linear history.

`git merge --no-ff`

This option `--no-ff` ensures that a merge commit is always created, even if the merge could be performed with a fast-forward. This helps keep the project's history more explicit and can make later code reviews or debugging easier.

## Git rebase

> [Merging vs. Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)

When we use `git rebase` and we are already on the branch which we want to rebase, we can skip a second argument. We can do:

```shell
git rebase main # instead of git rebase main feature
```

and the result will be

```shell
Before                        After
A---B---C---F---G (main)      A---B---C---F---G (main)
         \                                     \
          D---E (HEAD feature)                  D'---E' (HEAD feature)
```

> [!danger]
> Rebase changes commit hashes, D' and E' are new commits with different hashes from D and E.

## Remove changes

- `git reset --hard` removes staged and working directory changes.
- `git clean -fd` removes untracked directories in addition to untracked files.
- `git clean -nfd` does a dry run and tells you what would be deleted before actually deleting it.

## Delete branches

When you delete a local Git branch, it does not automatically delete the corresponding remote branch. The local and remote branches are managed separately, and deleting one does not affect the other.

Deleting local branches

```shell
git branch -d <branch-name>
git branch -D <branch-name> # for force deletion
```

Deleting remote branches

```shell
git push <remote-name> --delete <branch-name>
```

> [!warning]
> Before deleting a remote branch, ensure that other team members are not using it and approved.

## Update Git submodule to latest commit

Updating submodule in the parent repository:

```shell
git submodule update --remote <submodule-path>
```

Alternatively, navigating into the submodule directory and pull the changes directly:

```shell
cd <submodule-path>
git pull origin master  # or main, or any other branch name
```

## Rename a branch

```shell
git checkout old-branch-name
git branch -m new-branch-name
```

## Git stash

```shell
git stash
git stash save "message" # save changes with a descriptive message
git stash pop # reapply previously stashed changes
git stash apply # reapply changes but keep them in your stash
git stash apply n # reapply a specific stash with index n
git stash list
git stash show # view a summary of a stash
git stash show -p # view the full diff of a stash
git stash drop n # drop a specific stash with index n
git stash clear # drop all stashes
```

By default, running git stash will stash:

- changes that have been added to your index (staged changes)
- changes made to files that are currently tracked by Git (unstaged changes)

But it will not stash:

- new files in your working copy that have not yet been staged
- files that have been ignored

Adding the `-u` option tells `git stash` to also stash your untracked files:

```shell
git stash -u
git stash -a # also includes ignored files
```

> [!note]
> The stash is local to your Git repository; stashes are not transferred to the server when you push.
> It's recommended to use descriptive messages when creating stashes to easily identify them later.

## Delete "dangling" commits

While the commits after the reset point are no longer part of the branch's linear history, they still exist in the Git repository. They become "dangling" commits, which means they are not directly referenced by any branch.

```shell
# Step 1: Verify unreachable commits
git fsck --unreachable

# Step 2: Expire unreachable commits
git reflog expire --expire-unreachable=now --all

# Step 3: Run garbage collection
git gc --prune=now

# Step 4: Verify cleanup
git fsck --unreachable
```

> [!tip]
> If the commits are still reachable due to tags, branches, or other references, you need to delete those references first.

For remote repositories, you may need to force-push the changes to ensure the remote history is updated:

```shell
git push origin --force
```

## Create a tag

To merge your release branch into the main branch and create a tag, follow these steps:

```shell
git checkout main
git merge --no-ff release-branch-name
git tag -a v0.0.1
git push origin main
git push origin v0.0.1
```

## Undo a git rebase

### The short answer

First, use `git reflog` to find the commit where your branch was before the rebase started.

This command will show a list of recent actions in your repository. Look for the entry that indicates the start of the rebase.

```shell
222967b (HEAD -> main) HEAD@{0}: rebase (finish): returning to refs/heads/main
222967b (HEAD -> main) HEAD@{1}: rebase (squash): My big rebase
c388f0c HEAD@{2}: rebase (squash): # This is a combination of 20 commits
56ee04d HEAD@{3}: rebase (start): checkout HEAD~20
0a0f875 HEAD@{4}: commit: An old good commit
```

In this example, `HEAD@{3}` represents the start of the rebase, and `HEAD@{4}` is the commit before the rebase started.

Once you have identified the correct commit, reset your branch to that state:

```shell
git reset --hard HEAD@{4}
```

### Use the `ORIG_HEAD` pointer

Alternatively, when performing a rebase, git saves your starting point before the rebase as `ORIG_HEAD`.

This means that you can also use the following command:

```shell
git reset --hard ORIG_HEAD
```

> [!note]
> It must be noted however that the `git reset`, `git rebase`, and `git merge` commands all save the original HEAD pointer into `ORIG_HEAD`. This means that if you have used any of these commands following the rebase, you will instead have to use the `git reflog` to identify how to reset the branch.

## Recover a deleted branch

First, use `git reflog` to find the commit of the last commit on the deleted branch. The reflog output will look something like this:

```shell
abc1234 (HEAD -> main) HEAD@{0}: commit: Some recent commit message
def5678 HEAD@{1}: commit: Commit message from deleted branch
```

Then use the commit hash to create a new branch:

```shell
git checkout -b recovered-branch def5678
```

> [!tip]
> Using pipelines to filter the output. For example in PowerShell: `git reflog | Where-Object { $_ -match "launch\.json" }`.
