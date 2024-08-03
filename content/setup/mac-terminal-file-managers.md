---
title: Mac Terminal File Managers
draft: false
date: 2024-08-03
tags:
  - mac
  - tool
  - terminal
---

## Motivation

The terminal is the most-used tool for my daily work. Sometimes, I just want to navigate files and folders directly within the terminal. Therefore, a Terminal File Manager (TFM) is a necessary consideration to improve my productivity and streamline my tasks. On Windows, I use [tere](https://github.com/mgunyho/tere) for this purpose. After shifting to macOS, I am looking for an alternative to tere.

## Popular TFMs for macOS

There are several terminal file managers are recommended for macOS:

### Ranger

- [Ranger](https://ranger.github.io) is a versatile file manager with Vim-like keybindings
- Written in Perl, very old
- Customizable through Python scripts

### nnn

- [nnn](https://github.com/jarun/nnn) is a fast and lightweight file manager
- Tiny and requires nearly 0-config

### Lf

- [Lf](https://github.com/gokcehan/lf) stands for "List files"
- Written in Go, lightweight

### Yazi

- [Yazi](https://github.com/sxyazi/yazi) is a newer option written in Rust
- Leveraging non-blocking async I/O
- Modern and intuitive interface
- Good documentation

## Getting started

To install these tools on macOS, you can use package managers like Homebrew.

```shell
brew install nnn
```
After installation, simply type the name of the file manager in your terminal to launch it.

Some of the other useful shortcuts for nnn are:

|Shortcut | Utility                                                                                                                                                                                      |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| .   | toggle hidden files                                                                                                                                                                              |
| d   | toggle detail mode (show size, permissions and timestamps)                                                                                                                                       |
| q   | quit                                                                                                                                                                                             |
| /   | filter (press `/` and start typing to filter the contents of the current directory. It is very useful and quick. Press `/` twice, it changes to `\` and type a regular expression for filtering) |
| ‘   | first file match (press **`'`** and then a character to go to the first file/diectory starting with that character)                                                                              |
| ^n  | toggle type-to-navigate (type to filter and navigate, rather than commands)                                                                                                                      |
| B   | bookmark the current directory (`b` to list all bookmarked directories)                                                                                                                          |
| ~   | takes you home (pressing `~` again takes you back). `` ` `` takes you to root, `-` back and `@` start.                                                                                           |
| ^T  | toggle sort order (`d` enables the du (disk usage) mode where you can see the size of directories)                                                                                               |
| ]   | command prompt (`^]` for shell)                                                                                                                                                                  |
| ?   | get help on all the keyboard shortcuts and configuration                                                                                                                                         |

## Configure cd on quit

### Ranger

If you hit `Shift + S`, it opens a new shell on the current directory. Then if you hit `Ctrl + D` on the shell, it goes back to `ranger`. This workaround is often good enough.

### nnn

To set this up, place the following code in `~/.zshrc` file. This creates a new alias `n` for launching `nnn`. When launched with the new alias `n`, your terminal directory will be changed on quitting `nnn`.

```shell
n ()
{
    # Block nesting of nnn in subshells
    [ "${NNNLVL:-0}" -eq 0 ] || {
        echo "nnn is already running"
        return
    }

    # The behaviour is set to cd on quit (nnn checks if NNN_TMPFILE is set)
    # If NNN_TMPFILE is set to a custom path, it must be exported for nnn to
    # see. To cd on quit only on ^G, remove the "export" and make sure not to
    # use a custom path, i.e. set NNN_TMPFILE *exactly* as follows:
    #      NNN_TMPFILE="${XDG_CONFIG_HOME:-$HOME/.config}/nnn/.lastd"
    export NNN_TMPFILE="${XDG_CONFIG_HOME:-$HOME/.config}/nnn/.lastd"

    # Unmask ^Q (, ^V etc.) (if required, see `stty -a`) to Quit nnn
    # stty start undef
    # stty stop undef
    # stty lwrap undef
    # stty lnext undef

    # The command builtin allows one to alias nnn to n, if desired, without
    # making an infinitely recursive alias
    command nnn "$@"

    [ ! -f "$NNN_TMPFILE" ] || {
        . "$NNN_TMPFILE"
        rm -f -- "$NNN_TMPFILE" > /dev/null
    }
}
```

You can find more details [here](https://github.com/jarun/nnn/wiki/Basic-use-cases#configure-cd-on-quit).

### Yazi

Use the following `yy` shell wrapper that provides the ability to change the current working directory when exiting Yazi.

```shell
function yy() {  
	local tmp="$(mktemp -t "yazi-cwd.XXXXXX")"  
	yazi "$@" --cwd-file="$tmp"  
	if cwd="$(cat -- "$tmp")" && [ -n "$cwd" ] && [ "$cwd" != "$PWD" ]; then  
		builtin cd -- "$cwd"  
	fi  
	rm -f -- "$tmp"  
}
```

To use it, copy the function into the configuration file of your respective shell. Then use `yy` instead of `yazi` to start.

You can fine more details [here](https://yazi-rs.github.io/docs/quick-start#shell-wrapper).

## Learn more

- [Setup nnn on MacOS](https://umaranis.com/2023/09/07/setup-nnn-terminal-file-manager-on-macos/)
