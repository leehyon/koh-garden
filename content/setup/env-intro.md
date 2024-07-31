---
title: Environment Variables
date: 2024-07-10
tags:
  - windows
  - linux
---

Environment variables store data that's used by the operating system and other programs.

## Windows

Use the `Get-ChildItem Env:` cmdlet to see a full list of environment variables:

> [!attention]
> Unlike Windows, environment variables on macOS and Linux are case-sensitive. For example, `$env:Path` and `$env:PATH` are different environment variables on non-Windows platforms.

On Windows, environment variables can be defined in three scopes:

- Machine (or System) scope
- User scope
- Process[^1] scope

[^1]: The Process scope contains the environment variables available in the current process, or PowerShell session.

When you change environment variables in PowerShell, the change affects only the current session. This behavior resembles the behavior of the `Set` command in the Windows Command Shell and the `Setenv` command in UNIX-based environments. To change values in the Machine or User scopes, you must use the methods of the `System.Environment` class.

### Path information

The `$env:PATH` environment variable contains a list of folder locations that the operating system searches for executable files. On Windows, the list of folder locations is separated by the semi-colon (`;`) character. On non-Windows platforms, the colon (`:`) separates the folder locations in the environment variable.

```powershell
$Env:Path -split ';'
```

## Linux

The command used to display all the environment variables defined for a current session is `env`.

There are two ways to print the already defined environment variables:

- `printenv VARIABLE_NAME`
- `echo $VARIABLE_NAME`

The basic syntax to define an environment variable is as follows:

- `export VARIABLE_NAME=value`

However, the variables defined using this method are stored for the current session only.

### Persistent environment variables

To make environment variables persistent you need to define those variables in the bash configuration files.

- `/etc/environment` - Use this file to set up system-wide environment variables. Variables in this file are set in the following format: `VAR_TEST="Test Var"`
- `/etc/profile` - Variables set in this file are loaded whenever a bash login shell is entered. When declaring environment variables in this file you need to use the `export` command: `export JAVA_HOME="/path/to/java/home"`
- `~/.bashrc` - Per-user shell (Bash) specific configuration files

To load the new environment variables into the current shell session use the `source` command:

```bash
source ~/.bashrc
```
