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

## 2 Prgramming guessing game

```rust
use std::io;

fn main() {
    println!("Guess the number!");

    println!("Please input your guess.");

    let mut guess = String::new();

    io::stdin().read_line(&mut guess)
        .expect("Failed to read line");

        println!("You guessed: {}", guess);
}
```

In Rust variables are immutable by default. To create mutable variable you must use `mut` before variable name.

The syntax `::` indicates an associated function (static function) that is used here in `String::new`() and `io:stdin()`.

`&` indicates that this argument is a reference. References are immutable by default and hence `&mut` is used.

`expect` is a method of `io:Result`. If the Result is error thwn `expect` will cause the program to crash and display the given message.

Rust let's 'shadow' a variable name, meaning that you can instantiate a variable with an existing name. This is usually used when doing type conversion for example String -> u32.