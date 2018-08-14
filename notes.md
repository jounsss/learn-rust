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

# 3 Common Variable Concepts

## 3.1 Variables and Mutability

By default Rust variables are immutable ie. they cannot be changed once a value is assigned to them.

Examples:

```rust
let x = 5;
x = 6; // throws compiler error
```

```rust
let x = 5;
let x = 6; // works, variable shadowing
```

```rust
let x;
x = 5; // works because this is the first time a value is assigned to variable
```

```rust
let mut x = 5; // declare variable as mutable
x = 6; // works!
```

The difference between variables and constants `const` is that variables are by default immutable but constants are always immutable. You are not allowed to use mut with constants and contants must always have type assosiated with them.

```rust
const MX_VALUE: u32 = 100_000;
```

### 3.3 Data Types

*Scalar types* respresent a single value. Rust has four primary scalar types integer, floating-point, boolean and character.

**Integer** 

Signed integers can store numbers in range of [-2^(n-1), 2^(n-1)-1]. So a *i8* can store values [-128, 127].

Unsigned can store values from [0, 2^n-1]. So *i8* can have values [0, 255].

*Compound types* can groups multiple values into a single type.

**Tuple** is a collection that can contain multiple types of variables and once set cannot grow or shrink.

**Array** collections on the same type of variable and fixed length.

**Vector** is similar to Array but can grow or shrink in size;
