# android_device_xiaomi_pyxis
For building TWRP for Xiaomi Mi 9 Lite

TWRP device tree for Xiaomi Mi 9 Lite

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

## Compile

First checkout minimal twrp tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-11.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/pyxis" name="ne0sight/twrp_device_xiaomi_pyxis" remote="github" revision="android-11.0" />
```

Finally execute these:

```
. build/envsetup.sh
lunch twrp_pyxis-eng
mka recoveryimage
```

To test it:

```
fastboot boot out/target/product/pyxis/recovery.img
```

## Thanks

- Thanks to @PeterCxy for the commits and the base: https://github.com/PeterCxy/android_device_xiaomi_violet-twrp
- Thanks to @mauronofrio for initial pyxis twrp tree: https://github.com/mauronofrio/android_device_xiaomi_pyxis
