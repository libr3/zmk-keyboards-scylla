# Scylla ZMK Module

This repository contains the shield files for the [Scylla](https://github.com/Bastardkb/Scylla) to allow users to build firmware.

## Usage
Example, to build the left half (with ZMK Studio support):
```
west build -b nice_nano_v2 -S studio-rpc-usb-uart -- -DSHIELD=scylla_left -DZMK_EXTRA_MODULES="zmk-keyboards-scylla"
```
There is a full guide available for this here: [ZMK Modules Doc](https://zmk.dev/docs/features/modules)