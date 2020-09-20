## Big Sur :)

![oke](https://user-images.githubusercontent.com/54585187/91719734-106c4280-ebc0-11ea-8292-a1e8b4e883e3.png)

<img align="right" src="https://user-images.githubusercontent.com/54585187/91718709-22e57c80-ebbe-11ea-9d2b-9820924de92f.png" alt="Critter" width="550">
<img align="right" src="https://user-images.githubusercontent.com/54585187/91719259-29c0bf00-ebbf-11ea-89d5-852852793dcb.png" alt="Critter" width="550">
<img align="right" src="https://user-images.githubusercontent.com/54585187/91719410-7c01e000-ebbf-11ea-8aef-e2b42c2d1c18.png" alt="Critter" width="550">

# OpenCore BigSur Beta 5

## Download [here](https://github.com/KhaiZeRoFX/OpenCore-Dell-inspiron-3458/releases "vv")
## Laptop Specs
- Intel Core i3 5005u (Broadwell)
- GPU intel HD 5500
- Ram 4GB
- Intel AC3160
- Audio ALC 255
- Ethernet RTL8106E
## Working
- Wifi ([Itlwm](https://github.com/OpenIntelWireless/itlwm) Projects)
- Continuty (Handoff and Universal Clipboard)
- Native Power Management
- Bluetooth
- USB ports
- Battery status
- Keyboard & TrackPad
- Internal Audio & Microphone
- Headphone Jack
- HDMI Port (HDMI Audio)
- Graphics
- Sleep/Wake
- Ethernet
- Battery
- Bluetooth
- Icloud/Facetime/imessage
## Not Working
- Continuty (Airdrop)
- Brightness Control
- SD CARD (untest)
## Unknown issues
- intelbluetooth.kext got panic after put to OC
- Buggy intel Wifi - Bluetooth
- Slow intel wifi connection
- Some kext will caused Damage if dev not updating kext 

## Before Continue!!

Please use ProperTree for customize config file

(Don't use OpenCore Configuration, Clover Configuration or it will broke your config file)

## Pre Condition

**Bios configuration**
Bios Config | Setting 
:---:| :---:
Intel SpeedStep | Enabled
Virtualization    | Disabled
USB Wake Support | Disabled
SATA Operation | AHCI

## 1. Change DVMT settings (unneed because already patch 32mb DVMT)

Update your Bios to Lastest

1. Format USB as Fat32 and Copy EFI shell into it (Change EFI Shell name into EFI)

2. Boot with USB

3. At the grub prompt, enter these commands, hit enter after command, then exit and reboot

  `Setup_var 0x15B 0x3`
  
  `Setup_var 0x15C 0x3`
  
  ## *And now you have successfully changed the DVMT settings and fixed the kernel panic for graphics*
  
  # Wifi
  
  Download AirportItlwm from [this](https://github.com/OpenIntelWireless/itlwm)
  
  Put it to L/E with Hackintool
  
  ![h](https://user-images.githubusercontent.com/54585187/91720558-87eea180-ebc1-11ea-8026-57c8fb5dc0d0.png)
  
  Restart the PC
  
  After that go to System Preferences / Sercurity and enable kext
  
  ![g](https://user-images.githubusercontent.com/54585187/91720730-cf752d80-ebc1-11ea-99e3-a6d99ab3d7d4.png)
  
  # For more detail, pls go to this website
  
  https://dortania.github.io/OpenCore-Install-Guide/extras/big-sur/
