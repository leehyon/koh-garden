---
title: "VS Code FAQ"
tags:
  - faq
---

This section provides answers to commonly asked questions about VS Code.

## Variable substitution

VS Code supports variable substitution in **Debugging** and **Task** configuration files as well as some select settings. Variable substitution is supported inside some key and value strings in `launch.json` and `tasks.json` files using `${variableName}` syntax.

### Predefined variables

- `${userHome}` - the path of the user's home folder
- `${workspaceFolder}` - the path of the folder opened in VS Code
- `${file}` - the current opened file
- `${fileBasename}` - the current opened file's base name
- `${fileDirname}` - the current opened file's folder path

### Environment variables

- Through the `${env:Name}` syntax (for example, `${env:USERNAME}`).

### Configuration variables

- You can reference VS Code settings ("configurations") through `${config:Name}` syntax (for example, `${config:editor.fontSize}`).

## How to define and use custom variables

There are two methods: 

1. Define your environment variables and reference them using `${env:VARIABLE_NAME}`.
2. Add custom settings in `settings.json`, and reference those in `tasks.json` using `${config:myCustomVariable}`.
