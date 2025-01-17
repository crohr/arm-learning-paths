---
title: Introduction to Rust
weight: 2

### FIXED, DO NOT MODIFY
layout: learningpathall
---

## Rust, a safe programming language

Rust is a safe programming language with some key advantages:

* It is a modern, strong-typed language.
* Rust is memory safe by design: It is very difficult to introduce a bug like buffer overflow with Rust.
* Strict language: The Rust compiler is very strict and does not let you make easy mistakes like you might with C.
* The usage and support for Rust is expanding to many architectures and operating systems.

In this Learning Path you will learn the basics of how to program SIMD code on Arm using Rust.

## SIMD with Rust

Support for intrinsics in languages such as C and C++ is generally added by the compiler teams of each vendor, so for example, Arm compiler teams are responsible for adding support for Arm ISA intrinsics.

Rust is a little different in that regard. While vendors are still very involved in providing the support for SIMD intrinsics in the compiler, there are other alternatives and approaches used to provide SIMD abstraction.

Currently there are 2 SIMD programming interfaces in Rust:
* One under `std::arch` that follows the C intrinsics as much as possible.
* Another that provides a portable abstraction to SIMD programming so that code can just be recompiled across different architectures with more or less the same results. While there are similar libraries for C and C++, this is different in that the intent is for it to be merged as an official extension to the Rust standard library under `std::simd`.

In this Learning Path, you will learn how to use both of these interfaces to write code that uses Advanced SIMD/Neon instructions on an Arm CPU.

Before you start, first make sure you have the [Rust compiler installed](/install-guides/rust). 

You can check if you have a working `rustc` compiler installed by running:

```bash
rustc --version
```
Your output should look similar to:

```bash
rustc 1.79.0 (129f3b996 2024-06-10)
```

One of the interfaces you will use in this learning path is `std::simd`. Support for this feature currently exists only in `rustc` 'nightly' version. 

Switch to the `nightly` version to `rustc`:

```bash
rustup default nightly
```

Now run the version command again to check:

```bash
rustc --version
```
Your output should now look similar to:

```bash
rustc 1.82.0-nightly (92c6c0380 2024-07-21)
```

Now that you have a working Rust compiler with the features support in the nightly version, you can continue with building and running the examples included in this learning path. Please note that the code examples in this learning path are not optimally written for Rust. To do that you would have to use `cargo`, find the proper `crates` to do specific tasks, for example for 2D arrays, which would increase the complexity of this learning path significantly.
