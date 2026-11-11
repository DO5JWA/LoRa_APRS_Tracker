# DO5JWA LoRa APRS Tracker

**Extended fork of the [CA2RXU LoRa APRS Tracker](https://github.com/richonguzman/LoRa_APRS_Tracker)**  
**Independent TX/RX frequencies and LoRa parameters for ESP32-based trackers**

> **Tested hardware:** TTGO T-Beam V1.1 with SX1276. Other board variants have not yet been verified for this fork.

## Download firmware

### Ready-to-flash ESP32 image

**[Download DO5JWA LoRa APRS Tracker v1.0.0 – Complete firmware](https://github.com/DO5JWA/LoRa_APRS_Tracker/releases/download/v1.0.0-DO5JWA/DO5JWA_LoRa_APRS_Tracker_v1.0.0_full.bin)**

The complete image includes the bootloader, partition table, boot application data and application firmware. **Flash it at address `0x0000`.** No compilation is required.

[View the release notes and other downloads](https://github.com/DO5JWA/LoRa_APRS_Tracker/releases/tag/v1.0.0-DO5JWA)

## What's new in the DO5JWA fork?

- **Independent TX and RX frequencies:** Set different frequencies for transmitting and receiving.
- **Independent spreading factors (SF):** Configure TX and RX separately.
- **Independent coding rates (CR):** Configure TX and RX separately.
- **Independent bandwidths (BW):** Configure TX and RX separately.
- **Extended web configuration:** Adjust the additional LoRa parameters in the web interface.
- **Bluetooth connectivity fixes:** Improvements to Bluetooth connectivity.

### Tested configuration

| Component | Tested setup |
| --- | --- |
| Board | TTGO T-Beam V1.1 |
| LoRa transceiver | SX1276 |
| TX frequency | 433.775 MHz |
| RX frequency | 433.900 MHz |
| Result | Basic transmission and reception with separate frequencies verified |

## Installation on Windows

Use the **Espressif ESP32 Flash Download Tool** with the complete `.bin` file linked above.

### 1. Select the device

In the tool's initial window, choose:

- **ChipType:** ESP32
- **WorkMode:** Develop
- **LoadMode:** UART

### 2. Configure flashing

In the **SPIDownload** tab, select the downloaded `DO5JWA_LoRa_APRS_Tracker_v1.0.0_full.bin` in the first file row, enable its checkbox and enter the address below.

| Setting | Value |
| --- | --- |
| Flash address | `0x0000` |
| SPI SPEED | 40 MHz |
| SPI MODE | DIO |
| BAUD | 115200 |
| COM | Your T-Beam's USB serial port |

### 3. Flash and restart

1. Connect the TTGO T-Beam V1.1 to your computer using USB.
2. Select the correct COM port.
3. Click **START**.
4. Wait until **FINISH** appears.
5. Restart the T-Beam.

**Verified:** The complete image was successfully flashed using Espressif Flash Download Tool v3.9.11, and the T-Beam started successfully afterward.

> **Important:** Back up your device configuration before flashing. A full installation may overwrite existing settings. The separate `firmware.bin` is an application-only image, **not** a complete image for address `0x0000`.

## Original project and documentation

This repository is a fork of the original project developed by **Ricardo Guzman (CA2RXU)**. The original project includes additional supported hardware, features and a detailed development history.

- [Original CA2RXU LoRa APRS Tracker repository](https://github.com/richonguzman/LoRa_APRS_Tracker)
- [Original project wiki and documentation](https://github.com/richonguzman/LoRa_APRS_Tracker/wiki)
- [Original project release and development history](https://github.com/richonguzman/LoRa_APRS_Tracker)

**Note:** The original CA2RXU web flasher is intended for the upstream firmware. To install the **DO5JWA fork**, use the complete image and instructions above.

## Credits and license

Original project: **Ricardo Guzman (CA2RXU)** and its contributors.  
DO5JWA fork: additional independent TX/RX LoRa settings and Bluetooth-related changes.

This project retains the original **GPL-3.0** license. See the [LICENSE](LICENSE) file.

**73 de DO5JWA**
