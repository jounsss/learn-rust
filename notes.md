# Rust - notes

These are my notes on the rust tutorial at [https://doc.rust-lang.org/book/2018-edition/](https://doc.rust-lang.org/book/2018-edition/.)

## 1. Getting started

### 1.1 Installation

I installed rustup from Arch-repositories. When the package had installed a toolchain had to be installed and activated 

`rustup install stable` installs the stable toolchain

`rustup default stable` activates the stable toolchain

### 1.2 Hello, World!

`println!()` is a call to macro

`println()` is a call to function

### 1.3 Hello, Cargo!

Cargo is Rust's build system and package manager.

`cargo new <project-name>` creates a new Rust project. Rust project names cannot begin with a number.

`cargo build` build the project.

`cargo run` build and runs the project.

`cargo check` checks the code but does not produce an executable.