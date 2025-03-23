# WeActStudio.USB2CANFDV1

## SLCAN Protocol Description

> Using the virtual serial, the command is as follows:
- `O[CR]` - Opens the CAN channel
- `C[CR]` - Close the CAN channel
- `S0[CR]` - Set the nominal bit rate to 10k
- `S1[CR]` - Set the nominal bit rate to 20k
- `S2[CR]` - Set the nominal bit rate to 50k
- `S3[CR]` - Set the nominal bit rate to 100k
- `S4[CR]` - Set the nominal bit rate to 125k (default)
- `S5[CR]` - Set the nominal bit rate to 250k
- `S6[CR]` - Set the nominal bit rate to 500k
- `S7[CR]` - Set the nominal bit rate to 800k
- `S8[CR]` - Set the nominal bit rate to 1M
- `sddxxyyzz[CR]` - Custom nominal bit rate (60Mhz CAN clock)
- `Y0[CR]` - Set the CANFD data segment bit rate to 500k
- `Y1[CR]` - Set the CANFD data segment bit rate to 1M
- `Y2[CR]` - Set CANFD data segment bit rate to 2M (default)
- `Y3[CR]` - Set the CANFD data segment bit rate to 3M
- `Y4[CR]` - Set the CANFD data segment bit rate to 4M
- `Y5[CR]` - Set the CANFD data segment bit rate to 5M
- `yddxxyyzz[CR]` - Custom CANFD data segment bit rate (60Mhz CAN clock)
- `tIIILDD...[CR] `- Transfer data frame (standard ID) [ID, length, data]
- `TIIIIIIIILDD...[CR] `- Transfer data frame (extended ID) [ID, length, data]
- `rIIIL[CR]` - Transfer remote frame (standard ID) [ID, length]
- `RIIIIIIIIL[CR]` - Transfer remote frame (extended ID) [ID, length]
- `dIIILDD...[CR] `- Transmit CANFD standard frames (without BRS enabled) [ID, length, data]
- `DIIIIIIIILDD...[CR] `- Transmit CANFD extended frames (without BRS enabled) [ID, length, data]
- `bIIILDD...[CR] `- Transmit CANFD standard frames (BRS enabled) [ID, length, data]
- `BIIIIIIIILDD...[CR] `- Transmit CANFD extended frames (BRS enable) [ID, length, data]
- `V[CR]` - Reads the firmware version
- `X[CR]` - Enter firmware upgrade mode

`[CR]` : `0x0D` (hex), `\r` (ascii)

Please find more information in the `doc` directory or [wiki](https://github.com/Nakakiyo092/usb2canfdv1/wiki).

## How to compile firmware
Use STM32CubeIDE 1.18.0 or later.

## How to upgrade firmware
Use the upgrade tool in the root repository.

NOTE: After flashing this firmware, there would be an issue upgrading to another firmware.
You should manually send `X[CR]` command before upgrade or force upgrade mode by shorting DIO and GND as described in the root repository.
