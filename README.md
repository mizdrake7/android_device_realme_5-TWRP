# android_device_realme_r5x
For building TWRP for Realme 5 Series

TWRP device tree for Realme 5/5i/5s/5NFC

## Features

Works:

- ADB
- Decryption of /data
- Screen brightness settings
- Correct screenshot color
- MTP
- Flashing (opengapps, roms, images and so on)
- Backup/Restore (Needs more testing)
- USB OTG
- Vibration support
- External sdcard

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-12.1
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/realme/RMX1991" name="Amritorock/device_realme_r5x_recovery" remote="github" revision="android-13" />
```

Finally execute these:

```
. build/envsetup.sh
lunch twrp_r5x-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot flash recovery out/target/product/RMX1911/recovery.img
```

Then reboot to recovery

## Other Sources

Using precompiled stock kernel

## Thanks

