---
title: Setup Mac Terminal
date: 2024-08-03
draft: true
tags:
  - mac
  - terminal
---

## Motivation

Setting up a new Mac terminal can be a daunting task, especially when trying to recall previous configurations. This guide serves as a comprehensive reference for my personal setup, potentially benefiting others in the process.

## Prerequisites

- Install [Homebrew](https://brew.sh/) and git

> [!tip] Post-installation process for Homebrew
> After installing Homebrew, remember to execute the two steps in 'Next steps' as provided in the installation instructions.

## Setting up iTerm2 

- Install with `brew install --cask iterm2`
- Launch iTerm2 and go to Settings
	- Appearance
		- Theme: Minimal
		- Panes: 3
		- Dimming: 1 and 3
	- Profiles
		- General: Reuse previous session’s directory
		- Colors: Choose your preferred Color Preset

## Setting up oh-my-zsh

To manage plugins and themes related to zsh, it is a good idea to get a **framework** for managing these (sort of similar to Homebrew makes it easy to install, manage and update applications).

> [Oh My Zsh](https://github.com/ohmyzsh/ohmyzsh/wiki) is a delightful, open source, community-driven framework for managing your Zsh configuration. It comes bundled with thousands of helpful functions, helpers, plugins, themes, and a few things that make you shout...

Install oh-my-zsh via curl:

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### Plugins

Install the following plugins:

- zsh-autosuggestions
- zsh-completions
- fast-syntax-highlighting

First, clone the repositories into `$ZSH_CUSTOM/plugins` (by default `~/.oh-my-zsh/custom/plugins`):

```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

git clone https://github.com/zsh-users/zsh-completions ${ZSH_CUSTOM:-${ZSH:-~/.oh-my-zsh}/custom}/plugins/zsh-completions

git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting
```

Then add the plugins to the `~/.zshrc` file:

```shell
plugins=(
	git
	zsh-autosuggestions
	fast-syntax-highlighting
)
```

For zsh-completions, add the following to the `~/.zshrc` file:

```shell
fpath+="${ZSH_CUSTOM:-"$ZSH/custom"}/plugins/zsh-completions/src"
source "$ZSH/oh-my-zsh.sh"
```

> [!note]
> For more information on zsh-completions, refer to [this GitHub issue](https://github.com/ohmyzsh/ohmyzsh/issues/10412).

## Installing Starship

Starship is a cross-shell **prompt** that works with zsh.

1. Install with `brew install starship`
2. Add the following to your `~/.zshrc` file: `eval "$(starship init zsh)"`

Here's how your final `~/.zshrc` file should look:

```shell
plugins=(
	git
	zsh-autosuggestions
	fast-syntax-highlighting
)

fpath+=${ZSH_CUSTOM:-${ZSH:-~/.oh-my-zsh}/custom}/plugins/zsh-completions/src

source $ZSH/oh-my-zsh.sh

eval "$(starship init zsh)"
```

> [!note]
> Remember, you can customize this file further by adding your own aliases, functions, or environment variables after the Starship initialization. Also, if you have any specific Oh My Zsh settings you want to modify (like updating strategy, completion waiting dots, etc.), you can add those near the top of the file, before sourcing Oh My Zsh.

## Additional terminal tools

Consider installing additional terminal tools to enhance your workflow. For example, `nnn`is a terminal file manager. Refer to [[mac-terminal-file-explorer|my previous post]] for more detailed information on terminal tools for macOS.

## Learn more

- [macOS Terminal Tools](https://terminaltrove.com/categories/macos/)
- [如何从 0 开始配置 MacBook Pro](https://sorrycc.com/mac/)
- [Customize Your macOS Terminal Using Starship](https://developer.vonage.com/en/blog/customize-your-macos-terminal-using-starship)