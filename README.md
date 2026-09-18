# Kali NetHunter Pro for Nothing Phone (1) — Spacewar

> Device-specific development, build configuration, testing notes, and documentation for Kali NetHunter Pro on the Nothing Phone (1) (codename: `spacewar`).

[![Status](https://img.shields.io/badge/status-experimental-orange)](https://github.com/Pri-S-Godase/Kali-NetHunter-Pro-Nothing-Phone-1-Spacewar)
[![Platform](https://img.shields.io/badge/platform-Nothing%20Phone%201-blue)](https://github.com/Pri-S-Godase/Kali-NetHunter-Pro-Nothing-Phone-1-Spacewar)
[![Architecture](https://img.shields.io/badge/architecture-ARM64-green)](https://github.com/Pri-S-Godase/Kali-NetHunter-Pro-Nothing-Phone-1-Spacewar)
[![Kali](https://img.shields.io/badge/Kali-NetHunter%20Pro-purple)](https://www.kali.org/docs/nethunter-pro/)

## Overview

This project documents and develops a device-specific Kali NetHunter Pro environment for the Nothing Phone (1), codename **Spacewar**.

The work focuses on adapting the Kali NetHunter Pro build system to the device's Qualcomm platform and Android boot architecture, including device configuration, kernel compatibility, boot images, vendor boot, root filesystem, Phosh, and A/B slot testing.

This is an **independent community development project** and is not an official Kali Linux repository.

## Device

| Property | Value |
|---|---|
| Device | Nothing Phone (1) |
| Codename | spacewar |
| SoC | Qualcomm Snapdragon 778G+ |
| Qualcomm Platform | SM7325 |
| Architecture | ARM64 |
| Boot Image Header | v3 |
| Kernel Line | Linux 5.4.x |
| Partition Layout | A/B |
| Desktop Environment | Phosh |
| Project Status | Experimental |

## Goals

- Develop and document Kali NetHunter Pro support for Spacewar.
- Maintain device-specific build configuration.
- Document kernel and Android boot integration.
- Build and test boot and vendor_boot images.
- Document root filesystem deployment.
- Provide reproducible build and troubleshooting information.
- Record hardware compatibility and known limitations.
- Share findings with the open-source cybersecurity and mobile Linux community.

## Current Development

The project currently covers:

- Spacewar device configuration
- Qualcomm SM7325 platform configuration
- Android Boot Header v3
- Device-specific boot image generation
- vendor_boot and vendor ramdisk handling
- Kali NetHunter Pro root filesystem
- Phosh desktop environment
- Linux 5.4 kernel compatibility
- A/B slot and fastboot testing
- Installation and recovery documentation

## Repository Structure

```text
.
├── README.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── .gitignore
│
└── docs/
    ├── building.md
    ├── hardware.md
    ├── installation.md
    └── troubleshooting.md
```

## Build System

This project is based on the Kali NetHunter Pro build ecosystem. The upstream build scripts should be treated as the primary reference for general build-system behavior.

- Kali NetHunter Pro documentation: https://www.kali.org/docs/nethunter-pro/
- Kali NetHunter Pro build scripts: https://gitlab.com/kalilinux/nethunter/build-scripts/kali-nethunter-pro

Device-specific changes and findings will be documented in this repository rather than duplicating the complete upstream build system.

## Build

Start with the official Kali NetHunter Pro build requirements and then follow the Spacewar-specific notes in [docs/building.md](docs/building.md).

```bash
git clone https://github.com/Pri-S-Godase/Kali-NetHunter-Pro-Nothing-Phone-1-Spacewar.git
cd Kali-NetHunter-Pro-Nothing-Phone-1-Spacewar
```

## Installation

Installation requires an unlocked bootloader and a working fastboot environment.

**Warning:** Flashing partitions can cause data loss or leave the device unable to boot. Do not flash an image unless you understand the device's partition layout and have a recovery path.

See [docs/installation.md](docs/installation.md).

## Testing

Testing should record:

- Device model and codename
- Android/ROM version
- Active slot
- Kernel version
- Image build date/version
- Boot and vendor_boot versions
- Relevant `adb`, `fastboot`, and kernel logs
- Hardware features tested
- Exact steps that reproduce a problem

See [docs/troubleshooting.md](docs/troubleshooting.md).

## Project Status

| Component | Status |
|---|---|
| Spacewar identification | Complete |
| SM7325 configuration | Complete |
| Boot Header v3 configuration | Complete |
| Root filesystem | Testing |
| Boot image | Testing |
| vendor_boot | Testing |
| Kernel integration | Development/testing |
| Phosh | Testing |
| Hardware compatibility | Testing |
| Stable release | Not released |

Status will change as testing progresses.

## Safety and Responsible Use

Kali NetHunter is intended for authorized security testing, research, education, and development.

Only use security tools against devices, networks, applications, and accounts that you own or have explicit permission to test.

## Contributing

Issues, testing reports, documentation improvements, and code contributions are welcome.

Before submitting a device-specific change, include the relevant device/build information and explain how the change was tested.

See [CONTRIBUTING.md](CONTRIBUTING.md).

## Credits

This work builds on the Kali Linux and Kali NetHunter open-source ecosystem.

- Kali Linux
- Kali NetHunter
- Kali NetHunter Pro
- Linux kernel and Android open-source projects
- Nothing Phone (1) / Spacewar community development

## Disclaimer

This project is provided for development, research, and educational purposes. It is experimental software and may contain bugs or result in data loss or an unbootable device if used incorrectly.

Use it at your own risk and keep a complete backup of important data.

## Author

**Pri-S-Godase**

Cybersecurity-focused developer and open-source contributor.

GitHub: https://github.com/Pri-S-Godase
