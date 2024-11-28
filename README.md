# OpenCore EFI Setup for Microsoft Surface Laptop Go with macOS

> **Warning:** The **internal SSD** does **not work** for macOS on the Microsoft Surface Laptop Go. While you can attempt to install macOS on the internal SSD, it may fail. The recommended method is to install macOS on an external HDD (e.g., Seagate drive). You can consider replacing the internal SSD with a compatible one; guides are available online for this process.

This repository provides a fully functional OpenCore EFI configuration for running macOS on the **Microsoft Surface Laptop Go**. This setup allows macOS Ventura to be installed and run with support for essential features like Wi-Fi, audio, power management, and the touchpad.

## Features

- **macOS Compatibility**: Tested with **macOS Ventura** (YMMV with other versions like Monterey and Big Sur).
- **Wi-Fi**: Intel Wi-Fi support via **AirportItlwm** kext.
- **Audio**: Audio working with **VoodooHDA** (due to issues with AppleALC and ALC274 codec).
- **Power Management & Sleep**: Managed by **BigSurface.kext** (handles power management, touchpad, and sleep).
- **Touchpad**: Fully functional with **BigSurface.kext**.
- **iGPU**: Custom **iGPU.plist** for Intel UHD Graphics.

## Hardware Specifications

- **CPU**: Intel Core i5-1035G1 (Ice Lake).
- **GPU**: Intel UHD Graphics (Iris Plus Graphics G1).
- **RAM**: 8GB (soldered to motherboard).
- **Wi-Fi**: Intel Killer Wi-Fi 6 AX1650i (201NGW).
- **Audio**: Intel Ice Lake-LP Smart Sound Technology (Realtek ALC274 codec).
- **Touchpad**: ELAN.
- **SSD**: Samsung SSD, model MZ9LQ256HBJQ (128GB or 256GB NVMe M.2).
- **USB Ports**: USB 3.1 Gen 1 (Type-A and Type-C).
- **Display**: 12.4-inch PixelSense touchscreen.

## Installation

For installation instructions, please refer to the official [OpenCore Installation Guide](https://dortania.github.io/OpenCore-Install-Guide/) for detailed steps on setting up macOS with OpenCore.

> **Note:** The macOS installation was tested with **macOS Ventura**. Other macOS versions (such as Big Sur or Monterey) may work, but compatibility is not guaranteed.

## Kexts Used

- **AirportItlwm.kext**: Wi-Fi support for Intel cards.
- **AppleALC.kext**: Audio support (requires additional fixes).
- **BigSurface.kext**: Power management, touchpad, and sleep support.
- **VoodooHDA.kext**: Audio support for ALC274 codec.
- **VirtualSMC.kext**: SMC emulation for macOS.
- **Lilu.kext**: Core patching library for kext compatibility.
- **BlueToolFixup.kext**: Bluetooth compatibility.
- **ECEnabler.kext**: Embedded Controller support (disabled by default).

## Known Issues

- **Fingerprint Reader**: The fingerprint reader does not work as expected.
- **Internal SSD**: The internal SSD does not work with macOS, so you must install macOS on an external HDD (e.g., Seagate drive). If you wish to replace the internal SSD, guides are available online for this process.
- **Shutdown**: The shutdown functionality does not work as expected. The system may not properly shut down, requiring a hard reset.

## Troubleshooting

- **Audio**: If using macOS **Ventura** or **Big Sur 11.3+**, a fix may be required for audio to work. Please refer to the [discussion](https://www.tonymacx86.com) on fixing audio for ALC274.
- **Wi-Fi**: Ensure you're using the correct version of **AirportItlwm.kext** for your macOS version.
- **Touchpad**: If touchpad support is not working, ensure you have the **BigSurface.kext** installed correctly.
