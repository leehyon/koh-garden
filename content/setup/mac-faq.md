---
title: "Mac FAQ"
date: 2024-08-03
tags:
  - faq
  - mac
---

This section provides answers to the frequently asked questions that I have about Mac.

## Open Finder from anywhere

Just press `Option + Command + Space`, this opens a new Smart Finder window and it makes Finder the active app. From there, you can then press `Command + N` to open a regular Finder window.

Alternatively, you can create an Open Finder shortcut in [Automator](https://www.howtogeek.com/209225/automator-101-how-to-automate-repetitive-tasks-on-your-mac/). This [discussion](https://superuser.com/questions/406282/is-there-a-finder-shortcut-in-mac-like-the-windows-e-shortcut-to-bring-up-wind) walks you through the process.

## Open Finder in the current directory in zsh

Create an alias in your zsh configuration file (usually `~/.zshrc`):

```zsh
alias iii='open .'
```

Save the file and restart your terminal or run `source ~/.zshrc` to apply the changes.

## Terminal file manager

Please refer to [[mac-terminal-file-managers|this article]] for additional information.
