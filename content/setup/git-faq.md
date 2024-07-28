---
title: "Git FAQ"
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

## Git rebase

> [!danger]
> Using git rebase will change the commit IDs (hashes) of the rebased commits. 

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
git stash save "message" # Save changes with a descriptive message
git stash pop # Reapply previously stashed changes
git stash apply # Reapply changes but keep them in your stash
git stash apply n # Reapply a specific stash with index n
git stash list
git stash show # View a summary of a stash
git stash show -p # View the full diff of a stash
git stash drop n # Drop a specific stash with index n
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
> It's recommended to use descriptive messages when creating stashes to easily identify them later