# HP-Omen-15-DC-1xxxx-Hackintosh-Opencore

This project is dedicated to Opencore development on the HP Omen 15 DC-10008UA. In general this hackintosh project works on all HP Omen 15 DC-1xxxxx laptops with a UHD 630 and a proper SSD. 

![IMG_5100](https://user-images.githubusercontent.com/84881650/180301826-456d8baa-986c-4070-a097-81b5d4ed4c7d.jpeg)
![IMG_5099](https://user-images.githubusercontent.com/84881650/180301847-35a497ab-5682-43bb-b726-a19bf1499c77.jpeg)
![IMG_4645](https://user-images.githubusercontent.com/84881650/173489275-d11a2264-73df-493c-99b0-b4214e23a390.jpeg)
![![Screenshot 2022-06-14 at 04 59 27](https://user-images.githubusercontent.com/84881650/173489862-65fb6e78-cfee-4d56-8203-c84596c8b739.png)
![Screenshot 2022-06-14 at 04 56 49](https://user-images.githubusercontent.com/84881650/173489944-e32961d0-0837-4961-8d45-5c23dd7ecea7.png)
![Screenshot 2022-06-14 at 05 08 12](https://user-images.githubusercontent.com/84881650/173489867-583de278-32a9-4345-8fff-6988a80b878b.png)
![IMG_4641](https://user-images.githubusercontent.com/84881650/173489891-49daaa1c-a5bf-44ec-9a77-a76a5ec20344.jpeg)

# specifications
## Hardware specifications
### Motherboard

| Part  | Description |
| :-: | :-: |
| CPU     | Intel Core I5-9300H Coffeelake |
| IGPU    | Intel UHD 630 |
| DGPU    | Nvidia GTX 1650 |
| RAM     | 16GB 2667 MHz DDR4 SODIMM |
| NVME    | Toshiba KXG60znv256G (240GB) |
| SSD     | Samsung SSD 840 PRO Series (120GB) | 
| Display | 1080p IPS generic shit |
| Ethernet| Realtek RTL8111|
| Wireless| Broadcom BCM94352Z |
| Chipset | HM370 |

### peripherals   

| device type  | Description |
| :-: | :-: |
| pointer | Synaptics SMBus Touchpad |
| keyboard| Standard PS/2 Keyboard |
| Webcam | HP Wide Vision HD Camera |
| Cardreader | Realtek 522A |
|USB controller| PCH USB 3.1 xHCI Host Controller |
| Ports | 3x USB3.1 |
| | Type-c (Intel Linked)|
| | HDMI (Nvidia linked)|
| | Mini-Displayport (untested)|
| | AUX/MIC|
## Software specifications

| Version  | Description |
| :-: | :-: |
|Opencore version | 0.8.2 commit |
|MacOS version| 13.0 dev beta 1 |
|Bios version |F.23 Rev.A|
|Audio Codec |Realtek ALC295|

# Functionality
The functionality of the laptop that is tested and working is precisely described in the document "Checklist". 
underneath here you will find a general overview of what needs to be fixed, and also what is and what is not working.
- i lost the file somewhere on my laptop, will upload if i find it again!😓

### Graphical
- [x] IGPU Graphics acceleration 
- [x] Metal support
- [x] Backlight brightness control and smooth transitioning

### Audio
- [x] Speakers
- [x] Auxilary out
- [x] Auxilary in
- [x] Microphone

### Power
- [x] CPU power management
- [x] Manual/auto/lid sleep
- [x] Shutdown and restart
- [x] Battery readout
- [x] Battery charging

### Wireless
- [x] WIFI
- [x] Bluetooth
- [x] Airdrop
- [x] Handoff
- [x] Sidecar

### Disk
- [x] NVME working
- [x] SSD working
- [x] NVRAM
- [x] Trim support

### Peripherals
- [x] Trackpad (no trackpad buttons)
- [x] Keyboard (fn buttons need fixup)
- [x] Webcam
- [x] USB
- [x] Type-C (dongle non-functional)

### Services
- [x] Filefautling
- [x] System Intergrity Protection
- [x] Multibooting
- [x] Keyboard shortcuts 

## What needs to be fixed (Issues)

- [x] Type-c-to-HDMI dongle
- [x] trackpad buttons non-functional
- [x] "NON-HP battery" warning
- [x] Battery percentage Readout freeze
- [x] Battery not charging sometimes
- [ ] wake laptop by keyboard
- [ ] Can't turn on keyboard backlighting
- [x] replace wifi card with broadcom

### Optional
- [x] replace Intel wifi card with Broadcom
- [x] Buy Type-c-to-HDMI dongle
- [x] Enable Bootchime
- [ ] Fix RTC timezone difference between windows and MacOS


## What will never work
| What  | Why |
| :-: | :-: |
| dGPU | Apple dropped support for Nvidia webdrivers since High Sierra. Besides there were never MacOS drivers for the gtx 16-series.|
| HDMI | The built-in HDMI port on this laptop is linked to dGPU. Unfortunately, there are no drivers and the dGPU is disabled.|
|Airdrop| Airdrop and Handoff are not supported on Intel wifi chips. For this, a Broadcom wifi chip needs to be acquired.|

# Installation instructions
- download and mount a macos installer onto an usb stick using opencore guide online
- mount the efi partition of the usb stick with mountefi tool
- download and drop the efi folder of mine onto your usb stick
- using propertree and gensmbios, fill in the missing smbios details
- boot your hp omen into bios and put in the appropriate settings
- boot opencore from the usb and install macos using the installer
- after installation, mount the efi partition of the macos hard drive and usb and copy the efi from the usb onto the hard drive
- ready and done. unplug, reboot and stash that usb somewhere!

# references
🫥
https://dortania.github.io/OpenCore-Install-Guide/
