---
title: "Doxygen FAQ"
date: 2024-07-12
tags:
  - faq
  - doxygen
---

This section provides answers to commonly asked questions about Doxygen. Please begin by familiarizing yourself with the [[doxygen-coding-style|Doxygen coding style]].

## Expand AUTOSAR macros

By setting the following in the configuration file:

```c
ENABLE_PREPROCESSING   = YES
MACRO_EXPANSION        = YES
EXPAND_ONLY_PREDEF     = YES
PREDEFINED             = "FUNC(rettype,memclass)=rettype" \             
                         "VAR(type,memclass)=type" \
                         "P2VAR(ptrtype,memclass,ptrclass)=ptrtype *"
```

### Learn more

- [Doxygen: Preprocessing](https://www.doxygen.nl/manual/preprocessing.html)

## Add a Markdown file as the main page

1. Enable Markdown support in your Doxyfile.

2. Specify the Markdown file using the `USE_MDFILE_AS_MAINPAGE` option.

3. Make sure the Markdown file is included in the `INPUT` configuration.

```c
MARKDOWN_SUPPORT = YES
USE_MDFILE_AS_MAINPAGE = README.md
INPUT = README.md
```

If your Markdown file is in a different directory, provide the full path or add the directory to the INPUT configuration and set `RECURSIVE = YES`.

> [!important]
> `USE_MDFILE_AS_MAINPAGE` should only contain the file name, not the full path. The full path should be specified in the INPUT configuration if needed.

In your Markdown file, you can use a level 1 heading to create the main page title.

Or, you can use the `\mainpage` command, like so:

`manual/index.dox`

```c
/** \mainpage My Library Manual
- Building
- Basics
- Examples
*/
```

For other pages, prefix them with the `\page` command.

And then include it in your Doxyfile:

```c
INPUT  = manual/index.dox
```

## Add a module or topic description page

> [!note]
> To create custom pages, use one of the supported file extension: `.dox`, `.txt`, or `.md`. Doxygen will treat a `.dox` or `.txt` file as a C/C++ source file, and a `.md` file as a Markdown file.

If you prefer using Markdown files, create a `.md` file for your module description and include it in your Doxyfile:

```c
@ingroup group_name

# Module Title

Detailed description of the module goes here.
```

### Learn more

- [Doxygen: Additional Documentation](https://doxygen.nl/manual/additional.html)
