<div align="center">

# Electrum Doge

[![Python](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/)
[![Dogecoin](https://img.shields.io/badge/network-Dogecoin-C2A633)](https://dogecoin.com/)
[![GUI](https://img.shields.io/badge/gui-PyQt5-41CD52)](https://pypi.org/project/PyQt5/)
[![Platforms](https://img.shields.io/badge/platforms-Linux%20%7C%20macOS%20%7C%20Windows-lightgrey)](#boot)
[![License](https://img.shields.io/badge/license-MIT-green)](./UNLICENSE)

</div>

Dogecoin wallet codebase built on Electrum architecture: SPV sync, deterministic seeds, local signing, desktop-first flow.

## Snapshot

- Stack: Python, PyQt5, libsecp256k1, cryptography
- Model: SPV client, not a full Dogecoin node
- Entry point: `./run_electrum`
- Package target: desktop wallet
- Repo state: upstream mirror with local repo cleanup

## What It Does

- derives wallets from seed phrases
- restores existing deterministic wallets
- signs and broadcasts Dogecoin transactions
- connects to Electrum-compatible servers
- runs as a desktop GUI without a local blockchain copy

## Boot

```bash
git clone https://github.com/hachshiba/electrum-doge.git
cd electrum-doge
git submodule update --init --recursive
python3 -m pip install --user -e ".[gui,crypto]"
./run_electrum
```

## Build Notes

- Python `3.8+`
- `libsecp256k1` required
- `PyQt5` required for GUI
- local `libsecp256k1` build script: `./contrib/make_libsecp256k1.sh`
- test entry: `pytest electrum/tests -v`

## Layout

- `electrum/` core wallet code
- `contrib/` build and packaging helpers
- `run_electrum` local launcher
- `pubkeys/` signing and verification material

## License

MIT-style upstream license. See [UNLICENSE](/home/frank/githubs/GITS/electrodoge/UNLICENSE).
