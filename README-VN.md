<p align="center">
	<img src="https://iili.io/JCfJ3u.png" width="200" height="48"/>
</p>

-----

[![OpenCore](https://img.shields.io/badge/OpenCore-0.5.8-blue)](https://github.com/acidanthera/OpenCorePkg)
![Support-status](https://img.shields.io/badge/Support-YES-Green)

<img align="right" src="https://user-images.githubusercontent.com/54585187/80489711-7171d880-898a-11ea-9949-4075f348e6a9.png" alt="Critter" width="550">

<img align="right" src="https://user-images.githubusercontent.com/54585187/80489950-cf9ebb80-898a-11ea-8e96-1d91596e241d.png" width="550">

<img align="right" src="https://user-images.githubusercontent.com/54585187/80490256-49cf4000-898b-11ea-8d41-6c264a94633b.png" width="550">

# OpenCore Dell inspiron 3458
Opencore Hackintosh trên Dell inspiron 3458

*Ngôn ngữ:
- [English](https://github.com/KhaiZeRoFX/OpenCore-Dell-inspiron-3458 "EN")
- Tiếng Việt (Đang sử dụng)

## Tải ở [đây](https://github.com/KhaiZeRoFX/OpenCore-Dell-inspiron-3458/releases "vv")

## Cấu Hình Máy
- Intel Core i3 5005u (Broadwell)
- GPU intel HD 5500 (Fake to HD6000?)
- Ram 4GB
- Intel AC3160
- Audio ALC 255
- Ethernet RTL8106E
## Hoạt Động
- Native Power Management
- Bluetooth
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
## Không Hoạt Động
- SD card reader (untest)
- Wifi

## Lưu ý trước khi tiếp tục đọc bài này

Hãy dùng Xcode, ProperTree để sửa đổi file config của bạn

(Không được dùng OpenCore Configuration, Clover Configuration nếu không sẽ gây hỏng file config)

## Pre Condition

**Bios Settings**
Bios Config | Setting 
:---:| :---:
Intel SpeedStep | Enabled
Virtualization    | Disabled
USB Wake Support | Disabled
SATA Operation | AHCI

## 1. Thay đổi DVMT settings

Update bios của máy bạn lên phiên bản mới nhất

1. Format USB thành định dạng Fat32 và Copy EFI shell vào trong ổ đó (Đổi từ tên "EFI Shell" thành EFI)

2. Reset máy và Boot qua USB

3. Tại giao diện grub prompt, nhập các mã dưới đây, sau đó nhập lệnh "exit" và reboot máy

  `Setup_var 0x15B 0x3`
  
  `Setup_var 0x15C 0x3`
  
  ## *Và bây giờ bạn đã thành công trong việc Đổi DVMT và fix lỗi panic khi khởi động hackintosh*
  
  ## 2. Tạo USB boot
  (Mình sẽ dùng bản boot của Olarila)
  
  
  1. Tải MacOS Mojave từ [Olarila](https://drive.google.com/file/d/11XOoe-3Dcgqy97SJ3DGPSTx9Nz3LJIff/view "Olarila")
  
  2. Tải [Etcher](https://www.balena.io/etcher/ "this")
 
 3. Giải nén file ".raw"
 
 4. Mở Etcher, Chọn file olarila, chọn ổ cứng usb và flash (hãy sử dụng USB 16GB hoặc cao hơn)
 
 ![Etcher](https://user-images.githubusercontent.com/54585187/78206356-cc69fa00-74c8-11ea-87d4-f380bd9d2b66.gif)

## 3. Cài đặt OSX

1. Khi OC bootloader hiện ra, hãy chọn "Install OS mojave..." (hoặc gì đó)

2. Hệ thống sẽ tự động boot vào MacOS installer

3. Nếu đây là lần đầu cài đặt MacOS, làm ơn hãy Format sạch ổ cứng theo hướng dẫn ở dưới trước khi tiếp tục cài đặt

   a. Từ menu bar, chọn Utilities -> Choose Disk Utility
   
   b. Tìm ổ cứng mà bạn muốn cài macos lên đó, highlight nó
   
   c. Chọn Erase tab
   
   d. Ở phần Scheme: GUID Partition Map
   
   e. ở phần Name: Ghi một tên bất kì mà bạn muốn
   
   f. Ở phần Format: chọn định dạng APFS
   
   g. Click Erase
   
   h. Tắt Disk Utility
   
4. Chọn Continue, Continue, Agree

5. Chọn ổ cứng mà bạn muốn cài Macos Mojave và chọn Continue

6. Làm tách trà và đợi quá trình cài đặt xong :))

7. Nhấn nút F12 để chọn lại usb boot

8. Khi OC boot Option hiện lên, Chọn ổ cứng đã cài đặt macos

10. Đợi quá trình boot xong, setup các thứ, chuyển efi từ usb sang efi ổ cứng là xong :>

# Quan Trọng
(Sau khi cài đặt MacOS thành công, Làm ơn hãy đổi System info của bạn với ProperTree và Clover configuration generate)

<img align="" src="https://user-images.githubusercontent.com/54585187/80679059-5caa5780-8ae6-11ea-9ded-beed34526b00.png" width="600">
<img align="" src="https://user-images.githubusercontent.com/54585187/80678840-ead20e00-8ae5-11ea-8f9e-128a9ed6e1c5.png" width="600">
<img align="" src="https://user-images.githubusercontent.com/54585187/80679145-806d9d80-8ae6-11ea-86d9-27d675b92a2a.png" width="600">

# Audio
`nếu layout-id 7 không hoạt động, hãy thử id 11`

<img align="" src="https://user-images.githubusercontent.com/54585187/81153683-5bc56a00-8fad-11ea-8848-f942089825d6.png" width="600">

# ChimeBoot Sound

(nếu bạn đang thích thú bởi tiếng chime trên con realmac, ngại gi ko làm luôn nhể :>)
<img align="" src="https://user-images.githubusercontent.com/54585187/81152151-e016ed80-8fab-11ea-8574-5b0e665feef5.png" width="600">

## Nếu bạn muốn hỏi gì:
- [Opencore](https://dortania.github.io/OpenCore-Desktop-Guide/ "OpenCore") Guide
- Trang Web [Olarila](https://www.olarila.com "Olarila")
- [Olarila](https://www.facebook.com/groups/122585311156411 "Olarila") Facebook group
- Nếu bạn là người Việt Nam thì hãy vào [group](https://www.facebook.com/groups/224780132268974/?ref=share "group") này :B

## Credit
- [Apple](https://www.apple.com "Apple") for the Operation System
- [OpenCore](https://dortania.github.io/OpenCore-Desktop-Guide/misc/credit.html "OpenCore") for great Bootloader
- And for some other (i guess :v)
