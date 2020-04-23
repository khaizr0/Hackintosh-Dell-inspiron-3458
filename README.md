# OpenCore-Dell-inspiron-3458
OC hackintosh on Dell inspiron 3458
## Laptop Specs
- Intel Core i3 5005u (Broadwell)
- GPU intel HD 5500
- Ram 4GB
- AR9565 (DW1707)
- Audio ALC 255
- Ethernet RTL8106E
## Working
- Native Power Management
- Wifi
- USB ports
- Battery status
- Keyboard & TrackPad
- Internal Audio & Microphone
- Headphone Jack
- HDMI Port
- Graphics (Brightness Control)
- Sleep/Wake
- Ethernet
- Battery
- Bluetooth
- Icloud/Facetime/imessage
## Not Working
- SD card reader (untest)
- Bluetooth

![Macos](https://user-images.githubusercontent.com/54585187/80120095-ba094a80-85b4-11ea-9067-ca3c2fb19008.png)

## Before Continue Guide!!

Please use Xcode, ProperTree for customize config file

(Don't use OpenCore Configuration, Clover Configuration or it will broke your config file)

## Pre Condition

**Bios configuration**
Bios Config | Setting 
:---:| :---:
Intel SpeedStep | Enabled
Virtualization    | Disabled
USB Wake Support | Disabled
SATA Operation | AHCI

## 1. Change DVMT settings

Update your Bios to Lastest

1. Format USB as Fat32 and Copy EFI shell into it (Change EFI Shell name into EFI)

2. Boot with USB

3. At the grub prompt, enter these commands, hit enter after command, then exit and reboot

  `Setup_var 0x15B 0x3`
  
  `Setup_var 0x15C 0x3`
  
  ## *And now you have successfully changed the DVMT settings and fixed the kernel panic for graphics*
  
  ## 2. Create OSX Installer
  (I will use Olarila Mojave)
  
  ** Note: This OC can only run Mojave or Higher, Please don't run with older MacOS X
  
  1. Download MacOS Mojave From Olarila [here](https://drive.google.com/file/d/11XOoe-3Dcgqy97SJ3DGPSTx9Nz3LJIff/view "Here")
  
  2. Download [this](https://www.balena.io/etcher/ "this")
 
 3. Extract the .raw image
 
 4. Open Etcher, select image, select Drive and flash (Use USB 16GB or higher)
 
 ![Etcher](https://user-images.githubusercontent.com/54585187/78206356-cc69fa00-74c8-11ea-87d4-f380bd9d2b66.gif)

## 3. Install OSX

1. When OC boot screen appears, choose Install OS mojave ... (i guess)

2. The system will then boot into the OS X Installer

3. For a new installation of OS X, you MUST erase and format the destination drive according to the following steps before continuing.

   a. From the menu bar, click Utilities -> Choose Disk Utility
   
   b. Highlight your target hard drive for the High Sierra installation in left column.
   
   c. Click Erase tab
   
   d. Under Scheme: GUID Partition Map
   
   e. Under Name: type HD (You can name anything you want)
   
   f. Under Format: choose APFS
   
   g. Click Erase
   
   h. Close Disk Utility
   
4. Click Continue, Continue, Agree

5. Select name of your existing drive, where you want to install Macos Mojave and click Continue

6. Upon completion, system will restart

7. Press the F12 to choose boot device

8. Choose under UEFI Boot:

9. When OC boot screen appears, choose your existing name drive

10. After Booted successfull, copy your EFI folder from your USB to Hard drive and ready to go :)

## IF you wanna ask something: 
- [Opencore](https://dortania.github.io/OpenCore-Desktop-Guide/ "OpenCore") Guide
- [Olarila](https://www.olarila.com "Olarila") Website
- [Olarila](https://www.facebook.com/groups/122585311156411 "Olarila") Facebook group
- If you are VietNamese you can go to this [group](https://www.facebook.com/groups/224780132268974/?ref=share "group")

## Credit
- [Apple](https://www.apple.com "Apple") for the Operation System
- [OpenCore](https://dortania.github.io/OpenCore-Desktop-Guide/misc/credit.html "OpenCore") for great Bootloader
- And for some other (i guess :v)
