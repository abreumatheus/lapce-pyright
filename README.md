![Pyright](/assets/header.png)

# Pyright LSP for the Lapce editor

## Installing

### Pyright

The pyright language server must be available on the path. You can install it in many ways, choose the one you like the most in the [official guide](https://github.com/microsoft/pyright#command-line) (You must follow the "command line" section).

The most important part is that you need to have `pyright-langserver` on your path.

### Editor extension

You can install the extension directly via the Lapce editor, in the extensions tab. Just search for Python (pyright).

Obs: Don't forget to check the author name.

## Configuration

All additional functionality and configuration should work the same as described in the [README for pyright](https://github.com/microsoft/pyright).

The recommended way of configuring it would be be using a `pyproject.toml` file. You can see an example section bellow:

```toml
[tool.pyright]
venvPath = "./"
venv = ".venv"
reportMissingImports = true
reportMissingTypeStubs = false
typeCheckingMode = "off"
pythonVersion = "3.11.1"
```

## Build

Before building, you must ensure that you have the `wasm32-wasi` target setup.

```shell
rustup target add wasm32-wasi
```

### Debug

```shell
cargo build --target wasm32-wasi
```

### Release

```shell
cargo build --release --target wasm32-wasi
```

## Develop

### OSX / Linux

```shell
cd <lapse_dir>/dev.lapce.Lapce/plugins
```

```shell
mkdir lapce-pyright

cd lapce-pyright

ln -s <source_dir>/target/wasm32-wasi/debug/lapce-pyright.wasm ./bin/
```
