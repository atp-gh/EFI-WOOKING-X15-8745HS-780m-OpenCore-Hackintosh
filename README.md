# EFI WOOKING X15 8745HS 780M OpenCore Hackintosh

[English](README.md) | [简体中文](README_zh.md)

## OpenCore Version

[OpenCore 1.0.8](https://github.com/acidanthera/OpenCorePkg)

## Tested macOS Versions

- macOS Tahoe 26.0
- macOS Tahoe 26.7.3

## Hardware

| Component      | Specification                              |
| -------------- | ------------------------------------------ |
| Laptop         | WOOKING X15 (Generic / White-label Laptop) |
| CPU            | AMD Ryzen 7 8745HS                         |
| Integrated GPU | AMD Radeon 780M                            |
| Memory         | 16 GB (2 × 8 GB) DDR5-5600                 |
| Storage        | 512 GB OEM SSD                             |

## Projects Used

- [nullarc](https://github.com/luuumi-dev/nullarc): Provides integrated GPU support for the AMD Radeon 780M.

## Test Results

| Feature                         | Status        |
| ------------------------------- | ------------- |
| Metal 3                         | Supported     |
| VDA (Video Decode Acceleration) | Not Supported |
| Built-in Keyboard               | Working       |
| Touchpad                        | Working       |
| Wi-Fi                           | Not Working   |
| Bluetooth                       | Not Working   |
| HDMI Output                     | Issues        |
| Audio                           | Not Tested    |
| Microphone                      | Not Tested    |

### Additional Notes

- **Wi-Fi / Bluetooth:** The wireless card is a MediaTek MT7922. I tried several MT7922 drivers, but none worked. It is possible that my particular wireless card is faulty.
- **HDMI:** External display output is currently problematic.
- **VDA:** Video Decode Acceleration is not supported, despite Metal 3 support.

## Installation Guide

### 1. Install macOS

Use this EFI to boot the installer and complete the macOS installation normally.

### 2. Install nullarc GPU Support

After booting into macOS, install the GPU driver provided by [nullarc](https://github.com/luuumi-dev/nullarc).

Refer to the [official installation guide](https://github.com/luuumi-dev/nullarc#installing).

First, download the latest `nullarc-v0.4.0-alpha.zip` from the [Releases page](https://github.com/luuumi-dev/nullarc/releases).

Extract the archive, navigate to the extracted directory, and run:

```zsh
sudo ./install.sh --windowserver
```

Follow the on-screen instructions. You will need to enable automatic login for your user account.

After that, reboot the system twice. Once completed, the macOS desktop interface should be rendered using the Radeon 780M integrated GPU.

## Notes

For experimental validation of the Radeon 780M integrated GPU only. Details have not been fully optimized. Provided for reference purposes only.

## Acknowledgements

- [nullarc](https://github.com/luuumi-dev/nullarc)
- [mechrevo-wujie14pro-7840hs-780m-hackintosh-efi](https://github.com/bbbbrt/mechrevo-wujie14pro-7840hs-780m-hackintosh-efi)
