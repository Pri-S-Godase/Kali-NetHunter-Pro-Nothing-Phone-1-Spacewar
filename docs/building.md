# Building for Nothing Phone (1) — Spacewar

## Scope

This document records the device-specific build considerations for Spacewar. General Kali NetHunter Pro build behavior should be taken from the upstream project.

Upstream:
- https://www.kali.org/docs/nethunter-pro/
- https://gitlab.com/kalilinux/nethunter/build-scripts/kali-nethunter-pro

## Host

A Debian/Ubuntu-based Linux host is recommended.

Install the dependencies required by the current upstream NetHunter Pro build documentation before starting.

Useful Android/Linux tools include:

- git
- adb
- fastboot
- xz-utils
- 7z
- simg2img
- Android boot image utilities
- device-tree utilities

## Device Configuration

Spacewar uses:

- Qualcomm Snapdragon 778G+
- Qualcomm platform: SM7325
- ARM64
- Android boot image header version 3

The device-specific configuration should identify the correct Qualcomm platform and boot image format before an image is generated.

## Build Flow

The intended development flow is:

1. Prepare the Linux build host.
2. Clone the upstream Kali NetHunter Pro build system.
3. Select/configure the Spacewar device.
4. Apply Spacewar-specific device configuration.
5. Build the Kali root filesystem.
6. Build the kernel/device-specific components.
7. Generate the boot image.
8. Generate the vendor_boot image and vendor ramdisk.
9. Verify image metadata.
10. Test on the device using fastboot.
11. Record logs and results.

## Image Verification

Before flashing, inspect generated images and verify:

- image header version
- page size
- kernel size
- ramdisk size
- DTB/DTBO information
- vendor ramdisk contents
- expected architecture
- file checksums

Example tools used during development:

```bash
simg2img input.img output.raw.img
unpack_bootimg --boot_img boot.img
7z l archive.7z
```

Use the exact command syntax provided by the version of each tool installed on your host.

## Reproducibility

For each release/build, record:

- build date
- Git commit
- Android/ROM version
- kernel version
- rootfs version
- image filenames
- SHA256 checksums
- active fastboot slot
- known issues

Do not commit large generated images into Git. Publish release artifacts through GitHub Releases when appropriate.
