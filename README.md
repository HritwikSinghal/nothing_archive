# Nothing Phone (1) Archive

* A comprehensive collection of unmodified Full OTA update packages & stock OTA images for Nothing Phone (1).


## Downloads

- Downloads are tagged with POST_OTA_VERSION & NothingOS version [here](https://github.com/spike0en/Spacewar_Archive/releases). Please note that certain early releases for `T1.5` may lack `POST_OTA_VERSION` information. In such instances, downloads are provided with custom names, such as `Spacewar_T1.5_XXXXXX-XXXX_NothingOS Version`.

- Official Full OTA Update Package is marked `-FullOTA`. Extract the splitted 7z parts to get the `<name>-FullOTA.zip`.

## Categories

- The Stock OTA image files are categorized and archived in .7z format based on `boot`, `logical`, and `firmware` categories.
- The categorization mentioned below does not apply to version [2.5.5](https://github.com/spike0en/Spacewar_Archive/releases/tag/2.5.5) or the releases made prior to it. Users should manually relocate the `dtbo` image from the firmware > boot category folder after extraction for these specific releases. This has been resolved in subsequent releases.

### Boot (marked `-image-boot.7z`)

Includes 4 images:
```bash
boot, dtbo, vendor_boot & vbmeta
```
### Logical (marked `-image-logical.7z.001-003`)

Includes 6 images:
```bash
system, system_ext, product, vendor, odm, vbmeta_system & vbmeta_vendor
```
### Firmware (marked `-image-firmware.7z`)

Includes 18 images:
```bash
abl, aop, bluetooth, cpucp, devcfg, dsp, featenabler, hyp, imagefv, keymaster, modem, multiimgoem, qupfw, shrm, tz, uefisecapp, xbl & xbl_config
```

## Disclaimer

- While this is a collection of unmodified images, you still need to have the bootloader unlocked.

- You can re-lock the bootloader after flashing images.

- SHA-1 hash of `<name>-FullOTA.zip` file has been provided. It is to be noted that the built-in NothingOS Offline Updater Tool autonomously verifies file integrity. It initiates the update process only if the file aligns with the hash values specified in `payload-properties.txt`, which is obtained during the creation of the update package.

- For further inquiries, discussions, and engaging content, users are encouraged to explore the [Nothing Phone (1) Telegram Community](https://t.me/NothingPhone1)
  
## Fastboot Flashing

- To flash the stock, unmodified images with fastboot, extract the `.img` files using an utility such as [7zip](https://7-zip.org/download.html) and use the respective flashing script from [Nothing_Fastboot_Flasher](https://github.com/spike0en/Nothing_Fastboot_Flasher/tree/spacewar).

- The user must install the latest [Google USB drivers](https://developer.android.com/studio/run/win-usb) before flashing.
  
- If you optionally want to have dm-verity disabled, perform:

``` bash
fastboot update --disable-verity --disable-verification vbmeta.img
```
- Alternatively users can follow this [detailed flashing guide](https://telegra.ph/Guide-for-flashing-Stock-ROM-on-Nothing-Phone-2-04-22).

## Manual Sideloading of Full OTA Packages

### A. Via Stock Nothing Offline OTA Updater Tool (Locked BL): 

1. To flash stock, unmodified official Full OTA packages, extract the files using 7z to obtain the <name>-FullOTA.zip file.
2. Using your preferred file manager, create a folder named 'ota' at the root of your storage.
3. Copy the <name>-FullOTA.zip into the newly created 'ota' folder.
4. Open your dial pad and type `*#*#682#*#*`.
5. The manual update utility will launch, scanning and locating your previously downloaded update file.
6. Tap to begin the update. The process will take about 10-15 minutes (duration may vary).
7. Enjoy your updated device after reboot!

### B. Via Custom Recovery (Unlocked BL):

- Alternatively, users can directly flash these full OTA packages using available custom recoveries for Nothing Phone (1).


## Integrity Check

- You can check the downloaded file's integrity with one of the following commands (for logical):

``` bash
md5sum -c *-hash.md5
sha1sum -c *-hash.sha1
sha256sum -c *-hash.sha256
xxh128sum -c *-hash.xxh128
```

- xxh128 is usually the fastest.


### Thanks to
- [luk1337](https://github.com/luk1337/oplus_archive) & [arter97](https://github.com/arter97/nothing_archive) for their great work!
- [LukeSkyD](https://github.com/LukeSkyD) for ota link captures.
