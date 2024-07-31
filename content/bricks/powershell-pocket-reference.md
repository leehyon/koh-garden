---
title: PowerShell Pocket Guide
draft: false
date: 2024-07-31
tags:
  - pwsh
  - book
  - gist
aliases:
---

PowerShell is a powerful scripting language and command-line shell designed to simplify the management of systems. It stands out due to its unique features, such as **object-based** pipelines and deep integration with the .NET Framework.

## Structured commands

PowerShell commands, known as _cmdlets_, follow a consistent **Verb-Noun** naming convention:
- `Get-Process`: Retrieves information about processes running on a system
- `Set-Location`: Changes the current working directory
- `Get-Command *process*`: Finds out which PowerShell commands (and Windows applications) contain the word process
- `Get-Help Get-Process`: Finds out what a command such as Get-Process does

However, PowerShell has built-in aliases for many common Linux commands to ease the transition for users familiar with Unix-like systems. These aliases map to equivalent PowerShell cmdlets. Just type `Get-Alias` to get a list of all aliases.

Common Linux commands like `ls`, `cd`, `clear`, `cp`, `rm`, `echo`, and `cat` are typically aliased to their PowerShell equivalents by default.

## Deep integration of objects

Unlike traditional text-based shells, PowerShell works with objects. This means that the output of a command is not just plain text but a rich object that can be further manipulated.

```powershell
> $process = Get-Process notepad
> $process.Kill()
> "Hello World".Length
11
```

In this snippet, the string "Hello World" is treated as a fully functional object from the .NET Framework. It provides the `Get-Member` cmdlet to explore the properties and methods of these objects:

```powershell
> "Hello World" | Get-Member
```

## Navigating the system with providers

PowerShell also offers providers that allow you to navigate various data stores, such as the file system, registry, and more. For example, to navigate the Windows registry:

```powershell
> Set-Location HKCU:\Software\Microsoft\Windows\
> Get-ChildItem
```

## Miscellaneous

```powershell
> 0xFFE43A8
268321704
> 800GB / 2.2MB
372363.636363636
> [int] (3/2)
2
> "The answer is $(2+2)"
The answer is 4
```
