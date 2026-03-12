# Electrum Doge

[![Python](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/)
[![Dogecoin](https://img.shields.io/badge/network-Dogecoin-C2A633)](https://dogecoin.com/)
[![GUI](https://img.shields.io/badge/gui-PyQt5-41CD52)](https://pypi.org/project/PyQt5/)
[![Platforms](https://img.shields.io/badge/platforms-Linux%20%7C%20macOS%20%7C%20Windows-lightgrey)](#setup)
[![License](https://img.shields.io/badge/license-MIT-green)](./UNLICENSE)

## Description

Lightweight Dogecoin wallet derived from Electrum. Uses SPV, deterministic seeds, and a PyQt5 desktop interface. Full Dogecoin node is not required.

## Core Features

- SPV wallet operation over Electrum-style servers
- Deterministic seed-based wallet generation and recovery
- Transaction creation, signing, and broadcast
- PyQt5 desktop GUI
- Optional hardware wallet support
- Cross-platform source builds

## Setup

Requirements:

- Python `3.8+`
- `libsecp256k1`
- `PyQt5`
- `cryptography`

Install:

```bash
git clone https://github.com/hachshiba/electrum-doge.git
cd electrum-doge
git submodule update --init --recursive
python3 -m pip install --user -e ".[gui,crypto]"
```

Build `libsecp256k1` locally if needed:

```bash
sudo apt-get install automake libtool
./contrib/make_libsecp256k1.sh
```

## Usage

Start:

```bash
./run_electrum
```

Tests:

```bash
pytest electrum/tests -v
```

Non-editable install:

```bash
python3 -m pip install --user .
```

## Security Notes

- Protect seeds, keystores, and exported private keys.
- Verify source and remote before building binaries.
- Prefer deterministic build paths from `contrib/`.
- Review server configuration before production use.

## License

MIT-style license inherited from upstream. See [UNLICENSE](/home/frank/githubs/GITS/electrodoge/UNLICENSE).
