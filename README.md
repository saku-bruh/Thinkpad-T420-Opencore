# Lenovo ThinkPad T420 - OpenCore Configuation

![preview](https://github.com/saku-bruh/Thinkpad-T420-Opencore/blob/main/Resources/README/preview.png)

**05.07.2025:**<br/>
Initial public release<br/>

## Hardware:
**Display:** 1600x900 TN panel

**Audio:** Conexant CX20590

**RAM:** 8 GB 1600 MHz DDR3

**CPU:** Intel® Core™ i7-2640M

**GPU:** Intel® HD Graphics 3000

**Ethernet:** Intel® 82579LM Gigabit Ethernet

**Wi-Fi:** Intel® Centrino® Ultimate-N 6300

**Mobile** Connectivity (Not tested): F5521gw

**Bluetooth:** Broadcom BCM2045B

# Installation:<br/>

1. Copy the EFI folder to the USB, but before following Dortania's macOS install guide (i.e. before copying com.apple.recovery.boot and installing) you MUST do the following:
- Download [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
- Start GenSMBIOS
- Select the "2. Select config.plist" option
- Drag the config.plist from your USB in
- Select the "3. Generate SMBIOS" option
- Type in "iMac19,1"
- Then press enter and after that you're ready to install macOS
- After the system installation is completed, redo the steps above, with the exception of downloading GenSMBIOS, unless you deleted it. And instead of "iMac19,1" type in "MacBookPro8,1" the "3. Generate SMBIOS" and then you're ready boot into macOS<br/>

2. Install 15.x (use whichever version you are on, please do note that Tahoe is currently NOT supported by this EFI officially) [KdkSupportPkg](https://github.com/dortania/KdkSupportPkg)<br/>

3. Install patches using [OCLP-mod](https://github.com/laobamac/OCLP-Mod)<br/>
### NOTE: Do NOT use regular OCLP as it WILL fail patching for the Wi-Fi card on systems with Intel Wi-Fi, also if you have a BCM card (even though support for it is not added/disabled you may use the OCLP-mod from [this](https://www.mediafire.com/file/hu8dob0kcl1es8i/Items.zip/file) instead as it SUPPOSEDLY supports BCM Wi-Fi patching)

## Status

<details>  
<summary><strong>✅ What works?</strong></summary>
</br>

- [x] WiFi & Bluetooth (Intel as well as BCM requires spoofing for root patches, however BCM is not implemented since I have an Intel Wi-Fi card)
- [x] Audio (Audio Jack & Speaker)
- [X] Brightness / Volume Control
- [X] Built-in Microphone (May not detect sound on all apps)
- [X] Battery Information
- [X] USB Ports & Built-in Camera
- [X] Graphics Acceleration
- [X] Trackpoint / Touchpad (May be a bit jank though)
- [X] FaceTime / iMessage (iServices)
</details>

<details>
<summary><strong>⚠️ What doesn't work?</strong></summary>
</br>

- [ ] Hibernation (for now just run the 5 commands in [Dortania's Guide to fix sleep](https://dortania.github.io/OpenCore-Post-Install/universal/sleep.html#preparations), closing the lid will just turn off the screen and keep the laptop running, or if left for a longer period it'll enter a hibernation which it can't exit out of)
- [ ] DisplayPort (If plugged in on boot it will kernel panic and if the system is already up it won't display anything, as for VGA it hasn't been supported in macOS for ages)
</details>

<details>
<summary><strong>❌ What WON'T get fixed?</strong></summary>
</br>

- VGA (VGA hasn't been supported in macOS for years, thus it won't be fixed)
- Fingerprint Reader (No kext to spoof Touch ID)
</details>

<details>
<summary><strong>📋 Other Issues...</strong></summary>
</br>

- You may experience random lockups and/or light to heavy graphical glitches
- Monochrome widgets don't work
- Blur in some places (e.g. Terminal)
- DRM (Consider it half broken, it does work on Apple Music (e.g. Loseless Audio), with the exception of Dolby Atmos but it only partially works TV+, however due to graphical glitches it probably won't display correctly)

</details>
