# Scylla ZMK Module

This repository contains the shield files for the [Scylla](https://github.com/Bastardkb/Scylla) to allow users to build firmware.

There is a full guide available for this here: [ZMK Modules Doc](https://zmk.dev/docs/features/modules).

## Usage

By default, the module is built with the dongle as the central role, but the left side can be set as central by adjusting the build parameters, eliminating the need for a dongle.

### With dongle

To build the dongle (with ZMK Studio support):
```
west build -p -d build/dongle -b seeeduino_xiao_ble -S studio-rpc-usb-uart -- -DSHIELD=scylla_dongle -DZMK_EXTRA_MODULES="/absolute/path/to/zmk-keyboards-scylla"
```
To build the left half:
```
west build -p -d build/left -b nice_nano_v2 -- -DSHIELD=scylla_left -DZMK_EXTRA_MODULES="/absolute/path/to/zmk-keyboards-scylla"
```
To build the right half:
```
west build -p -d build/right -b nice_nano_v2 -- -DSHIELD=scylla_left -DZMK_EXTRA_MODULES="/absolute/path/to/zmk-keyboards-scylla"
```
To build reset settings:
```
west build -p -d build/reset -b nice_nano_v2 -- -DSHIELD=settings_reset -DZMK_EXTRA_MODULES="/absolute/path/to/zmk-keyboards-scylla"
```
To build reset settings (dongle):
```
west build -p -d build/reset_dongle -b seeeduino_xiao_ble -- -DSHIELD=settings_reset -DZMK_EXTRA_MODULES="/absolute/path/to/zmk-keyboards-scylla"
```

### Without dongle

To build the left half (with ZMK Studio support):
```
west build -p -d build/left -b nice_nano_v2 -S studio-rpc-usb-uart -- -DSHIELD=scylla_left -DZMK_EXTRA_MODULES="/absolute/path/to/zmk-keyboards-scylla" -DCONFIG_ZMK_KEYBOARD_NAME=\"Scylla\" -DCONFIG_ZMK_SPLIT_ROLE_CENTRAL=y -DCONFIG_ZMK_USB=y -DCONFIG_ZMK_SPLIT_BLE_CENTRAL_PERIPHERALS=1 -DCONFIG_ZMK_SPLIT_BLE_CENTRAL_BATTERY_LEVEL_FETCHING=y -DCONFIG_ZMK_SPLIT_BLE_CENTRAL_BATTERY_LEVEL_PROXY=y
```
To build the right half:
```
west build -p -d build/right -b nice_nano_v2 -- -DSHIELD=scylla_right -DZMK_EXTRA_MODULES="/absolute/path/to/zmk-keyboards-scylla"
```
To build reset settings:
```
west build -p -d build/reset -b nice_nano_v2 -- -DSHIELD=settings_reset -DZMK_EXTRA_MODULES="/absolute/path/to/zmk-keyboards-scylla"
```


