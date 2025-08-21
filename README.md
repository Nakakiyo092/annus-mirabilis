# WeActStudio.USB2CANFDV1

This repository contains sources for the slcan USB2CANFDV1 firmware. This firmware implements non-standard slcan commands to support CANFD messaging alongside a LAWICEL-style command set.

## Frequently Used Commands

- `O[CR]` - Opens the CAN channel
- `C[CR]` - Closes the CAN channel
- `sddxxyyzz[CR]` - Sets custom nominal bit rate
- `yddxxyyzz[CR]` - Sets custom CANFD data segment bit rate
- `tiiildd...[CR] `- Transmits base frame
- `Tiiiiiiiildd...[CR] `- Transmits extended frame
- `diiildd...[CR] `- Transmits CANFD base frame (BRS disabled)
- `Diiiiiiiildd...[CR] `- Transmits CANFD extended frames (BRS disabled)
- `biiildd...[CR] `- Transmits CANFD base frames (BRS enabled)
- `Biiiiiiiildd...[CR] `- Transmits CANFD extended frames (BRS enable)
- `V[CR]` and `v[CR]` - Returns firmware version and remote path as a string
- `Z[CR]` and `z[CR]` - Configures reporting mechanism including time stamp and Tx event
- `M[CR]` and `m[CR]` - Configures CAN acceptance filter
- `F[CR]` and `f[CR]` - Returns status flags and detailed status
- `X[CR]` - Enters firmware upgrade mode

`[CR]` : `0x0D` (hex), `\r` (ascii)

Please find more information in the `doc` directory or the [wiki](https://github.com/Nakakiyo092/usb2canfdv1/wiki).

## How to compile firmware
Use STM32CubeIDE 1.18.0 or later.

## How to upgrade firmware
Use the upgrade tool in the [root repository](https://github.com/WeActStudio/WeActStudio.USB2CANFDV1).

Note: After flashing this firmware, there would be an issue upgrading to another firmware.
You should manually send `X[CR]` command before upgrade or force upgrade mode by shorting DIO and GND as described in the root repository.
