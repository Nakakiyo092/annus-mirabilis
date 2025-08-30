# _Annus mirabilis_

This project is derived from [usb2canfdv1](https://github.com/Nakakiyo092/usb2canfdv1) which was forked from [WeActStudio.USB2CANFDV1](https://github.com/WeActStudio/WeActStudio.USB2CANFDV1).

## Purpose

This software was created to prove the ability to poll a CAN FD frame using a remote frame.

## Usage

- Setup this device and open the port following the method described in [this](https://github.com/Nakakiyo092/usb2canfdv1) project.

- Connect CAN line to another device to communicate with this device.

- Send a remote frame with CAN ID `0x19050630` and with DLC `0xE` (48 bytes) from the other device.

- Confirm the following 48 bytes of data is received on the other device on the bus.

    `HEX: 5A 75 72 20 45 6C 65 6B 74 72 6F 64 79 6E 61 6D 69 6B 20 62 65 77 65 67 74 65 72 20 4B 6F 65 72 70 65 72 00 00 00 00 00 00 00 00 00 00 00 00 00`

## How to compile firmware

Use STM32CubeIDE 1.18.0 or later.

## How to upgrade firmware

Use the upgrade tool in the [root repository](https://github.com/WeActStudio/WeActStudio.USB2CANFDV1).

Note: After flashing this firmware, there would be an issue upgrading to another firmware.
You should manually send `X[CR]` command before upgrade or force upgrade mode by shorting DIO and GND as described in the root repository.
