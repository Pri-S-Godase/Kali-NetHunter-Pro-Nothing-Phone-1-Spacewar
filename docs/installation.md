# Installation — Spacewar

> **Experimental software. Read the complete procedure before flashing anything.**

## Requirements

- Nothing Phone (1) / Spacewar
- Unlocked bootloader
- Working USB connection
- Recent Android platform-tools
- Known-good backup of important data
- A recovery/fastboot restoration path

## Before Flashing

Check the current slot:

```bash
fastboot getvar current-slot
```

Also record the existing boot/vendor_boot images and ROM version whenever possible.

Do not assume that an image built for another ROM, Android version, kernel, or device configuration is compatible with your current installation.

## Development Flashing

The following is an example development workflow, not a universal installation command set:

```bash
fastboot flash userdata <rootfs-image>
fastboot flash boot_a <boot-image>
fastboot flash vendor_boot_a <vendor-boot-image>

fastboot set_active a
fastboot reboot
```

**Do not execute these commands blindly.** Partition names, image compatibility, slot state, and required partitions can vary with the ROM and build.

## If the Device Returns to Bootloader

Collect:

```bash
fastboot getvar all
```

and record:

- current slot
- slot bootable state
- slot successful state
- retry count
- bootloader/firmware version

Do not repeatedly flash random images. Restore a known-good boot chain first, then isolate the failing component.

## Recovery

Always keep a known-good ROM/boot image and the vendor-specific restoration instructions available before testing development builds.

If the device becomes unbootable, use the appropriate official/community recovery procedure for the ROM currently installed on the device.

## Data Safety

Flashing userdata may erase user data. Maintain backups before testing.
