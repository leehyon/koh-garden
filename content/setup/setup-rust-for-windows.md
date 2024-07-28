---
title: Rust for Windows
draft: false
tags:
  - rust
  - setup
  - windows
---

Rust is a **systems** programming language, so it's used for writing systems (such as operating systems). In addition, Rust is designed around the promise of guaranteed memory safety, without the need for garbage collection.

The pieces of the Rust development toolset and ecosystem:

- A **crate** is a Rust unit of compilation and linking. A crate can exist in source code form, and from there it can be processed into a crate in the form of either a binary executable, or a binary library.
- A Rust project is known as a **package**. A package contains one or more crates, together with a `Cargo.toml` file that describes how to build those crates.
- `rustup` is the installer and updater for the Rust toolchain.
- **Cargo** is the name of Rust's package management tool.
- `rustc` is the compiler for Rust. Most of the time, you won't invoke `rustc` directly; you'll invoke it indirectly via Cargo.
- [crates.io](https://crates.io/) is the Rust community's crate registry.

## Set up development environment

> [!tip]
> We recommend that you do your Rust development on Windows. However, if you plan to locally compile and test on Linux, then developing with Rust on the WSL is also an option.

On Windows, Rust requires certain C++ build tools.

> [!note]
> Rust requires a native linker to be available on your system. On Linux or Unix systems (such as macOS), Rust calls `cc` for linking, whereas on Windows, the linker of choice is Microsoft Visual Studio's linker, which depends on having Microsoft Visual C++ Build Tools installed. While it's possible to use an open source toolchain on Windows as well, this exercise is left for more advanced users.

You can either download the [Microsoft C++ Build Tools](https://visualstudio.microsoft.com/visual-cpp-build-tools/), or you might prefer just to install [Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/) (recommended).

> Use of the Microsoft C++ Build Tools, or Visual Studio Build Tools, requires a valid Visual Studio license (either Community, Pro, or Enterprise).

While installing Visual Studio, there are several Windows workloads that we recommend you select:

- `.NET desktop development`, 
- `Desktop development with C++`, and 
- `Universal Windows Platform development`. 

You might not think that you'll need all three, but it's likely enough that some dependency will arise where they're required that we feel it's just simpler to select all three.

### Install Rust

Rust is installed via the [rustup](https://rustup.rs/) installer, which supports installation on Windows, macOS, and Linux.

Rust follows a release cycle where stable, beta, and nightly channels are available for developers. 

> Rust nightly refers to a version of the Rust programming language that is under active development. It is called "nightly" because it is released on a daily basis.

Rust works very well on Windows, so there's no need for you to go the WSL route (unless you plan to locally compile and test on Linux). Since you have Windows, we recommend that you just run the `rustup` installer for 64-bit Windows. Also install the Microsoft C and C++ (MSVC) toolchain by running `rustup default stable-msvc`. You'll then be all set to write apps for Windows using Rust.

```shell
# Check the version of the Rust compiler
rustc --version
# Add the --verbose argument for more details
rustc --version --verbose
# Get the local Rust documentation
rustup doc
# Update to a newly released version
rustup update
# Uninstall Rust and rustup
rustup self uninstall
```

### Rust in VS Code

By using VS Code as your text editor (or IDE), you can take advantage of language services such as code completion, syntax highlighting, formatting, and debugging.

- After you've installed VS Code, install the `rust-analyzer` extension.
- For debugging support, install the `CodeLLDB` extension.

> [!note]
> An alternative to the `CodeLLDB` extension for debugging support is the Microsoft `C/C++` extension. The `C/C++` extension doesn't integrate as well with the IDE as `CodeLLDB` does. But the `C/C++` extension provides superior debugging information. So you might want to have that standing by in case you need it.

## Install Rust via Scoop

> [!danger]
> If you must use Scoop, please choose `rustup-msvc` or `rustup`, and use `rustup update` to keep it updated.

The logic of Scoop is to manage the apps (located in the `apps` folder) and the accompanying generated data (located in the `persist` folder) in a unified place (which is the main directory of Scoop), without making any modifications to other parts of the system except for environment variables and shortcuts (as far as I know, this is how it works according to official buckets).

`rustup` is used to manage the installation, update, and uninstallation of all Rust components (including itself). These components are located in the `.cargo` and `.rustup` directories, and `rustup-init.exe` will retrieve the locations of these two directories based on environment variables.

Although `cargo` and `rustc` are executable "software", Scoop considers the paths `.cargo` and `.rustup` to be data associated with the `rustup` software. It will place these two directories in persist (and also add `cargo\bin` to `$env:PATH`).

If you install `rustup` using Scoop and no longer update it with Scoop, then there is no difference between using `rustup-init.exe` for installation. The only difference is that during installation, you choose to place `.cargo` and `.rustup` in the location `scoop\persist`, and all future updates will be handled by `rustup` itself. However, from the perspective of Scoop, the version of `rustup` remains at the time of last installation (actually not true, as it can update itself). If you continue to use Scoop to update `rustup` after installation, both Scoop and `rustup` will consider that `rustup` has been updated to the latest version, while other components of rust still need to be updated using `rustup`.

## Rust for Linux

Before you install Rust, you need to install one dependency, the `build-essential` package.

> [!note]
> Because Rust needs a linker to link all object files produced by the Rust compiler into an executable binary. The build-essential package contains a linker that'll get the job done.

```bash
sudo apt update && sudo apt install build-essential
```

Here's the command to install and run the rustup script:

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

After a while, the script will finish and ask you to update the PATH variable to include the Cargo bin directory. You can do that using the source command:

```bash
source "$HOME/.cargo/env"
```

## Lear more

- [Introduction - The rustup book](https://rust-lang.github.io/rustup/index.html)
- [The Rust Programming Language](https://doc.rust-lang.org/book/title-page.html)
- [Rust with Visual Studio Code](https://code.visualstudio.com/docs/languages/rust)
- [Developing with Rust on Windows](https://learn.microsoft.com/en-us/windows/dev-environment/rust/)
- [Microsoft C++ Build Tools - Visual Studio](https://visualstudio.microsoft.com/visual-cpp-build-tools/)
- [Getting started - Rust Programming Language](https://www.rust-lang.org/learn/get-started)
