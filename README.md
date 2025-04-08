# WeActStudio.USB2CANFDV1

## SLCAN Protocol Description

Using the virtual serial, the command is as follows:
- `O[CR]` - Opens the CAN channel
- `C[CR]` - Closes the CAN channel
- `S0[CR]` - Sets the nominal bit rate to 10k
- `S1[CR]` - Sets the nominal bit rate to 20k
- `S2[CR]` - Sets the nominal bit rate to 50k
- `S3[CR]` - Sets the nominal bit rate to 100k
- `S4[CR]` - Sets the nominal bit rate to 125k (default)
- `S5[CR]` - Sets the nominal bit rate to 250k
- `S6[CR]` - Sets the nominal bit rate to 500k
- `S7[CR]` - Sets the nominal bit rate to 800k
- `S8[CR]` - Sets the nominal bit rate to 1M
- `sddxxyyzz[CR]` - Custom nominal bit rate (60Mhz CAN clock)
- `Y0[CR]` - Sets the CANFD data segment bit rate to 500k
- `Y1[CR]` - Sets the CANFD data segment bit rate to 1M
- `Y2[CR]` - Sets the CANFD data segment bit rate to 2M (default)
- `Y3[CR]` - Sets the CANFD data segment bit rate to 3M
- `Y4[CR]` - Sets the CANFD data segment bit rate to 4M
- `Y5[CR]` - Sets the CANFD data segment bit rate to 5M
- `yddxxyyzz[CR]` - Custom CANFD data segment bit rate (60Mhz CAN clock)
- `tiiildd...[CR] `- Transmits data frame (standard ID) [ID, length, data]
- `Tiiiiiiiildd...[CR] `- Transmits data frame (extended ID) [ID, length, data]
- `riiil[CR]` - Transmits remote frame (standard ID) [ID, length]
- `Riiiiiiiil[CR]` - Transmits remote frame (extended ID) [ID, length]
- `diiildd...[CR] `- Transmits CANFD standard frames (without BRS enabled) [ID, length, data]
- `Diiiiiiiildd...[CR] `- Transmits CANFD extended frames (without BRS enabled) [ID, length, data]
- `biiildd...[CR] `- Transmits CANFD standard frames (BRS enabled) [ID, length, data]
- `Biiiiiiiildd...[CR] `- Transmits CANFD extended frames (BRS enable) [ID, length, data]
- `V[CR]` - Reads the firmware version
- `X[CR]` - Enters firmware upgrade mode

`[CR]` : `0x0D` (hex), `\r` (ascii)

Please find more information in the `doc` directory or the [wiki](https://github.com/Nakakiyo092/usb2canfdv1/wiki).

## How to compile firmware
Use STM32CubeIDE 1.18.0 or later.

## How to upgrade firmware
Use the upgrade tool in the [root repository](https://github.com/WeActStudio/WeActStudio.USB2CANFDV1).

Note: After flashing this firmware, there would be an issue upgrading to another firmware.
You should manually send `X[CR]` command before upgrade or force upgrade mode by shorting DIO and GND as described in the root repository.
