# Troubleshooting

## Device boots back to fastboot

Record:

```bash
fastboot getvar current-slot
fastboot getvar all
```

Check:

- boot image compatibility
- vendor_boot compatibility
- kernel compatibility
- DTB/DTBO compatibility
- active slot
- AVB/verified boot configuration
- ROM and Android version

## Slot State

Useful fastboot information includes:

```text
current-slot
slot-unbootable
slot-successful
slot-retry-count
```

A slot that is marked unbootable or has exhausted its retry count may require restoration of a known-good boot chain.

## Inspecting boot images

Use an appropriate `unpack_bootimg` implementation:

```bash
unpack_bootimg --boot_img <boot-image>
```

Record the header version, page size, kernel size, ramdisk size, and DTB information.

## Inspecting vendor_boot

A vendor_boot image can contain:

- vendor ramdisk
- device tree information
- vendor-specific boot metadata

Verify that the vendor ramdisk and DTB correspond to the target Spacewar build.

## Collecting Android Logs

If the system boots far enough for ADB:

```bash
adb devices
adb shell getprop
adb shell uname -a
adb logcat -b all
```

For kernel-related failures, capture the available kernel logs before rebooting.

## Reporting a Bug

A useful issue should include:

1. Device: Nothing Phone (1)
2. Codename: Spacewar
3. Android/ROM version
4. Kernel version
5. NetHunter build/version
6. Active slot
7. Image versions/checksums
8. Exact flashing steps
9. Expected behavior
10. Actual behavior
11. Relevant logs

Never include private keys, account credentials, tokens, or other sensitive information in an issue.
