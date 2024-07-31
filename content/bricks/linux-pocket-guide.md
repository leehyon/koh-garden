---
title: Linux Pocket Guide
draft: false
date: 2024-07-30
tags:
  - linux
  - book
  - gist
aliases:
---

> [!tldr]
> Sharing my reading notes from the book _Linux Pocket Guide_ by Daniel J. Barrett. Check out them for practical takeaways to improve your Linux skills!

## Getting help

| Command | Utility |
| :------------- | :------------- |
| `man wc`       |  |
| `man -k database \| less` | Search by keyword |
| `info ls`       |  |
| `wc --help`       | Many Linux commands respond to the option `--help` |

- If the output is longer than the screen, pipe it into the `less` program to display it in pages.
- Your friend, the `echo` command: `echo My name is $USER`.

## Linux: A first view

- Linux has four major parts:
  1. The kernel
  2. Supplied programs
  3. The shell
  4. X

- To determine the version of the Linux operating system:
  - `cat /etc/*release`
  - `uname -a`
  - `hostnamectl`

- In Linux, all files and directories descend from the root (`/`).

- There are several ways to locate or refer to your home directory:
  - `cd` with no arguments
  - `$HOME` variable
  - `~`

| Directory     | Description     |
| :------------- | :------------- |
| /usr/sbin | Programs (usually binary files) intended to be run by the superuser |
| /etc  | Configuration files for the system (and other miscellaneous stuff)  |
| /dev  | Device files for interfacing with disks and other hardware  |
| /var  | Files specific to this computer, created and updated as the computer runs |
| /proc | Operating system state |

- Files in `/proc` are used mostly by programs, but feel free to explore them.
  - `cat /proc/version`
- To see the ownership and permissions of a directory, add the `-d` option.
  - `ls -ld mydir`
  - `-rwxr-x---` means a file (`-`) that can be read (`r`), written (`w`), and executed (`x`) by the owner, read and executed by the group, and not accessed at all by other users.
- To see who’s logged into the computer, type `who`.
- To change password of current user, type `passwd`.
- To display hostname of the system, type `hostname`.
- To list all processes sorted by their current system resource usage, type `top`.

## Shell features

- Use `type` command to tell a command is a shell builtin or a program.
- Use `export` command to make a variable and its value available to other programs.
- To run a sequence of commands, but stop execution if any of them fails, separate them with `&&` symbols.
  - `command1 && command2 && command3`
- Single quotes treat their contents literally, while double quotes let shell constructs be evaluated.
  - Backquotes cause their contents to be evaluated as a shell command.
  - A dollar sign and parentheses are equivalent to backquotes.
- A job is simply the shell's unit of work.
  - Jobs are at a higher level than Linux processes, the Linux operating system knows nothing about them.
  - Type `^Z` in a shell, while a job is running in the foreground, will suspend that job. It simply stops running, but its state is remembered.
    - Now you're ready to type `bg` to put the command into the background, or `fg` to resume it in the foreground. You could also leave it suspended and run other commands.
  - Type `^C` to kill a command running in the foreground immediately.
  - Type `^D` to terminate a shell, either run the `exit` command.

```bash
who | wc -l
echo $SHELL
PATH=$PATH:/usr/sbin
echo $PATH
type who
export MYVAR=3
printenv HOME
echo This year is `date +%Y`
echo This year is $(date +%Y)
history 10
history -c # Clear (delete) your history
jobs
bg %2
```

## File operations

- Use `ls` to list files in a directory.
  - The `-a` option displays all files
  - The `-l` option produces a long listing
  - The `-S` option sorts files by their size
  - The `-t` option sorts files by the time they were last modified

- Use `cp` to copy a file.
  - The `-a` or `-r` option for recursively copying directories

- Use `cat` to view files in their entirety.
- Use `less` to view text files one page at a time.
- Use `head` to view the first lines of a text file.
- Use `tail` to view the last lines of a text file.

```bash
find /var/www -name '*.css' # find files by name
grep font /var/www/html/style.css # find files containing text
grep -R font /var/www/html/ # grep recursively for a directory
```
