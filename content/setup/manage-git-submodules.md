---
title: Manage Git Submodules
draft: false
date: 2024-07-10
tags:
    - git
---

> [!important]
> If you make changes to a submodule's repository, be sure to commit and push those changes **separately**. Then, in your main project, commit the updated reference to the submodule.
> Submodules are indeed particularly well-suited for repositories that are **rarely updated** and **stable**.

## Common commands

```shell
# Add a submodule
git submodule add <url> <path>
git submodule add -b <branch> <url> <path>
# Initialize and clone the submodule
git submodule init
git submodule update
# Change the URL of a submodule
git submodule set-url <path> <new-url>
# Update .gitmodules after changes
git submodule sync
```

To update the submodule to the latest commit, **navigate to the submodule directory** and use `git pull` or `git checkout <branch>` to update it.

## Remove the submodule

```shell
git submodule deinit <path_to_submodule>
git rm <path_to_submodule>
git commit -m "Removed submodule"
rm -rf .git/modules/<path_to_submodule>
```

> [!tip]
> `deinit` 命令如果添加上参数`-f`，则子模块工作区内即使有本地的修改，也会被移除。建议还是 `cd` 到子模块文件夹 `git stash`。

## Submodule workflows

Once submodules are properly initialized and updated within a parent repository they can be utilized exactly like **stand-alone repositories**. This means that submodules have their own branches and history. When making changes to a submodule it is important to **publish submodule changes and then update the parent repositories** reference to the submodule.

If you are working in a team environment it is critical that you then `git push` the submodule updates, and the parent repository updates.

## Alternatives to submodule

> Which is best for you depends on your needs, desires, and workflow. They are in some senses semi-isomorphic, it is just some are a lot easier to use than others for specific tasks.
> - [gitslave](http://gitslave.sf.net/) is useful when you control and develop on the subprojects at more of less the same time as the superproject, and furthermore when you typically want to tag, branch, push, pull, etc all repositories at the same time. gitslave has never been tested on windows that I know of. It requires perl.
> - [git-submodule](https://www.kernel.org/pub/software/scm/git/docs/git-submodule.html) is better when you do not control the subprojects or more specifically wish to fix the subproject at a specific revision even as the subproject changes. git-submodule is a standard part of git and thus would work on windows.
> - [git-subtree](https://github.com/apenwarr/git-subtree) provides a front-end to git's built-in subtree merge strategy. It is better when you prefer to have a single-repository "unified" git history. Unlike the subtree merge strategy, it is easier to export changes to the different (directory) trees back out to the original project, but it is not as automatic as it is with gitslave or even git-submodule.
> - [repo](https://gerrit.googlesource.com/git-repo/) is in theory similar to gitslave, but not as well documented for non-android operations that I have found. It is fairly dedicated to the Google Android development model and only natively supports a handful of git commands (though you can run arbitrary commands) and the limited native support doesn't support, for example, a centralized repository to push to and checking out a branch seems fairly difficult.
> 👉 [git subtree - Alternatives to Git Submodules? - Stack Overflow](https://stackoverflow.com/a/6500559)

## Learn more

- [Git Subtree](https://www.atlassian.com/git/tutorials/git-subtree)
- [Git LFS - large file storage](https://www.atlassian.com/git/tutorials/git-lfs)
