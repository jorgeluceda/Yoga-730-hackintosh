# Yoga-730-hackintosh
This Clover config work for Lenovo Yoga 730-13IKB

## Credits
Clover config based on the files of @Rehabman: https://github.com/RehabMan/OS-X-Clover-Laptop-Config

## What's not working
* Hibernation
* USB Type-C hot plug
* Active Pen
* Intel WLan 8265-AC (Replaced by BCM94352z)

## Working
* Intel Graphic UHD620 inject `0x591b0000` to `ig-platform-id`, [WhateverGreen.kext](https://github.com/acidanthera/WhateverGreen/releases)
* Realtek ALC236 inject Layout-id `15` [AppleALC.kext](https://github.com/acidanthera/AppleALC/releases)
* TouchPad and TouchScreen work, [VoodooI2C.kext](https://github.com/alexandred/VoodooI2C/releases). 

When touchpad not work, you should enter command `sudo kextcache -system-prelinked-kernel` in terminal and reboot
* USB [USBInjectAll.kext](https://bitbucket.org/RehabMan/os-x-usb-inject-all/downloads)
* Intel Blooth works when reboot from windows
* SSD Trim by Clover patch 
* Camera works fine

## Before install Mac OS X
* Disable Intel SGX and Intel Platform Trust in BIOS
* Switch RAID to AHCI 
* Follow Clover patch is necessary to touchpad
```
<dict>
    <key>Comment</key>
    <string>change _OSI to XOSI, pair with SSDT-XOSI.aml</string>
    <key>Disabled</key>
    <false/>
    <key>Find</key>
    <data>X09TSQ==</data>
    <key>Replace</key>
    <data>WE9TSQ==</data>
</dict>
<dict>
    <key>Comment</key>
    <string>change SBFBSBFI to SBFBSBFG</string>
    <key>Disabled</key>
    <false/>
    <key>Find</key>
    <data>U0JGQlNCRkk=</data>
    <key>Replace</key>
    <data>U0JGQlNCRkc=</data>
</dict>
```