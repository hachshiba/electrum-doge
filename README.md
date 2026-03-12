# Electrum Doge

[![Python](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/)
[![Dogecoin](https://img.shields.io/badge/network-Dogecoin-C2A633)](https://dogecoin.com/)
[![GUI](https://img.shields.io/badge/gui-PyQt5-41CD52)](https://pypi.org/project/PyQt5/)
[![Platforms](https://img.shields.io/badge/platforms-Linux%20%7C%20macOS%20%7C%20Windows-lightgrey)](#setup)
[![License](https://img.shields.io/badge/license-MIT-green)](./UNLICENSE)

## Description

Electrum Doge is a lightweight Dogecoin wallet derived from the Electrum codebase. It provides SPV-based wallet operation, deterministic key management, and a desktop GUI without requiring a full Dogecoin node.

## Core Features

- Deterministic wallet generation and recovery from seed phrases
- SPV verification against Electrum-compatible Dogecoin servers
- Desktop GUI via PyQt5
- Transaction creation, signing, and broadcast
- Optional hardware wallet integrations through extra dependencies
- Cross-platform packaging for Linux, macOS, Windows, and Android

## Setup

System requirements:

- Python `3.8+`
- `libsecp256k1`
- `PyQt5` for the GUI
- `cryptography` for accelerated crypto operations

Clone and install:

```bash
git clone https://github.com/hachshiba/electrum-doge.git
cd electrum-doge
git submodule update --init --recursive
python3 -m pip install --user -e ".[gui,crypto]"
```

If `libsecp256k1` is not available from your package manager:

```bash
sudo apt-get install automake libtool
./contrib/make_libsecp256k1.sh
```

## Usage

Run the wallet from the repository root:

```bash
./run_electrum
```

Run tests:

```bash
pytest electrum/tests -v
```

Install as a user package instead of editable mode:

```bash
python3 -m pip install --user .
```

## Security Notes

- Verify the repository remote before building or publishing binaries.
- Treat wallet seeds, keystores, and exported private keys as sensitive material.
- Prefer reproducible or deterministic build paths from `contrib/` for release artifacts.
- Review server configuration and network defaults before production use.

## License

MIT-style licensing inherited from the upstream Electrum codebase. See [UNLICENSE](/home/frank/githubs/GITS/electrodoge/UNLICENSE).
