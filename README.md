# Yoga-730-hackintosh

This Clover config work for Lenovo Yoga 730-13IKB

## Credits

Clover config based on the files of @Rehabman: https://github.com/RehabMan/OS-X-Clover-Laptop-Config

## What's not working

* Hibernation
* USB Type-C hot plug
* Active Pen
* Intel WLan 8265-AC

## Working

* Intel Graphic UHD620 inject `0x591b0000` to `ig-platform-id`, [WhateverGreen.kext](https://github.com/acidanthera/WhateverGreen/releases)
* Realtek ALC236 inject Layout-id `15` [AppleALC.kext](https://github.com/acidanthera/AppleALC/releases)
* TouchPad and TouchScreen work, [VoodooI2C.kext](https://github.com/alexandred/VoodooI2C/releases). 
* USB [USBInjectAll.kext](https://bitbucket.org/RehabMan/os-x-usb-inject-all/downloads)
* Intel Blooth works when reboot from windows
* SSD Trim by Clover patch 
* Camera works fine

## BIOS setting before install

* Disable Security -> Intel SGX -> Intel SGX Controller
* Disable Security -> Secure Boot
* Switch RAID to AHCI in Configuration -> SATA Controller Mode

## FAQ

- Q: Touchpad not work on First boot?  
  A: Enter command `sudo kextcache -system-prelinked-kernel` in terminal and reboot
- Q: Can't boot Win10 when BIOS swtch to AHCI?  
  A: Boot Win10 in [Safe Mode](https://support.microsoft.com/help/12376) 
