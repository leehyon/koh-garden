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

> Type `$PSVersionTable` to check your version of PowerShell.

## Structured commands

PowerShell commands, known as _cmdlets_, follow a consistent **Verb-Noun** naming convention:
- `Get-Process`: Retrieves information about processes running on a system
- `Set-Location`: Changes the current working directory
- `Get-Command *process*`: Finds out which PowerShell commands (and Windows applications) contain the word process
- `Get-Help Get-Process`: Finds out what a command such as Get-Process does

However, PowerShell has built-in aliases for many common Linux commands to ease the transition for users familiar with Unix-like systems. These aliases map to equivalent PowerShell cmdlets. Just type `Get-Alias` to get a list of all aliases.

Common Linux commands like `ls`, `cd`, `clear`, `cp`, `rm`, `echo`, and `cat` are typically aliased to their PowerShell equivalents by default.

### Cmdlets, functions and applications

1. A _cmdlet_ is a native PowerShell command-line utility. These exist only inside PowerShell and are written in a .NET Core language such as C#.
2. A _function_ can be similar to a cmdlet, but rather than being written in a .NET language, functions are written in PowerShell's own scripting language.
3. An _application_ is any kind of external executable, including command-line utilities such as `ping` and `ipconfig`.

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

A PowerShell provider, or _PSProvider_, is an adapter. It's designed to take some kind of data storage, and make it look like a disk drive. You can see a list of installed PowerShell providers right within the shell:

```powershell
> Get-PSProvider
Name                 Capabilities                                      Drives
----                 ------------                                      ------
Registry             ShouldProcess                                     {HKLM, HKCU}
Alias                ShouldProcess                                     {Alias}
Environment          ShouldProcess                                     {Env}
FileSystem           Filter, ShouldProcess, Credentials                {C, D, Temp, E…}
Function             ShouldProcess                                     {Function}
Variable             ShouldProcess                                     {Variable}
```

You use a provider to create a PSDrive. A _PSDrive_ uses a single provider to connect to data storage.

### Understanding how the filesystem is organized

PowerShell and Linux have some differences in how they handle and refer to the filesystem. Because a PSDrive might not point to a filesystem, PowerShell doesn't use the terms file and folder. Instead, it refers to these objects by the more generic term item. Items can, and often do, have properties. Knowing those facts should help you make sense of the verbs and nouns in the command list we showed you earlier.

## Finding and installing modules

Modules are self-contained units designed for easy distribution. Microsoft has introduced a module called _PowerShellGet_, which provides similar functionality to popular package managers in Linux such as rpm, yum, and apt-get. The central repository for PowerShell content is the [PowerShell Gallery](https://www.powershellgallery.com/), where users can discover, install, update, and publish PowerShell packages. The PowerShellGet module includes cmdlets to facilitate these actions with packages from the PowerShell Gallery.

- **Terminal-Icons**: Adds file and folder icons to the PowerShell terminal, enhancing visual feedback
- **posh-git**: Enhances PowerShell's Git integration, showing Git status in the prompt and providing Git command auto-completion
- **ImportExcel**: Import/export Excel spreadsheets, without Excel

## PowerShell profiles

PowerShell profiles are scripts that can be used to customize the PowerShell environment when the shell starts. A PowerShell hosting application, such as the console or VS Code, allows users to send commands to the PowerShell engine, which executes the commands and displays the results. The hosting application is responsible for loading and running profile scripts each time the shell starts.

Profile scripts can be used to perform various customizations, such as loading modules, changing the starting directory, or defining functions.

Details are available if you run `help about_profiles`, but you mainly need to consider whether you'll be working in multiple different hosting applications. For example, we tend to switch back and forth between Windows Terminal, and VS Code. We like to have the same profile running for both.

```powershell
> $Profile | Format-List -force

AllUsersAllHosts       : C:\Program Files\PowerShell\7\profile.ps1
AllUsersCurrentHost    : C:\Program Files\PowerShell\7\Microsoft.PowerShell_profile.ps1
CurrentUserAllHosts    : $home\Documents\PowerShell\profile.ps1
CurrentUserCurrentHost : $home\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
Length                 : 71
```

Because we want the same shell extensions to load whether we're using the console host or the VS Code, it's recommended to customize `$home\Documents\WindowsPowerShell\
profile.ps1`.

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
