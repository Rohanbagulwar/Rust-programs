# Python-Rust Integration with PyO3 and Maturin

This project demonstrates how to integrate Rust with Python using the PyO3 library. We will create a Rust library, compile it into a Python package using `maturin`, and then install and use it in a Python environment.

## Prerequisites

Ensure you have the following installed:
- Rust (latest stable version) → Install via [rustup](https://rustup.rs/)
- Python (3.7 or later)
- `pip` and `virtualenv` (optional but recommended for isolated environments)
- `maturin` → Install using:
  ```sh
  pip install maturin

Project Setup
1. Create a New Rust Project
cargo new --lib python_rust
cd python_rust

2. Modify Cargo.toml
Update Cargo.toml to include PyO3 dependencies and configure the library:

 ```sh
[package]
name = "python_rust"
version = "0.1.0"
edition = "2024"
[lib]
name = "python_rust"  # Must match #[pymodule] name
crate-type = ["cdylib"]

[dependencies]
pyo3 = { version = "0.20.0", features = ["extension-module"] }
