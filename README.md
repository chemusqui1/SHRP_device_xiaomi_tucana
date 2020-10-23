# android_device_xiaomi_tucana
For building TWRP for Xiaomi Mi Note 10

TWRP device tree for Xiaomi Mi Note 10

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
- Android Q Support
- Themes support
- Vibration

TO DO:

- Password and PIN decryption on Android R stock ROM (Pattern decrypts succesfully)


## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/tucana" name="chemusqui1/android_device_xiaomi_tucana" remote="github" revision="main" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_tucana-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot boot out/target/product/tucana/recovery.img
```

## Other Sources

Precompiled Stock One

## Thanks

Thanks to @mauronofrio for initial device tree
