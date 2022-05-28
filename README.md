# HP-Omen-15-DC-1xxxx-Hackintosh-Opencore

This project is dedicated to Opencore development on the HP Omen 15 DC-10008UA. In general this hackintosh project works on all HP Omen 15 DC-1xxxxx laptops with a UHD 630 and a proper SSD. 
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
| Wireless| Intel Wireless AC 9560 160Mhz |
| Chipset | HM470 |

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
|Opencore version | 0.8.1 |
|MacOS version| 12.4 |
|Bios version |F.23 Rev.A|
|Audio Codec |Realtek ALC295|

# Functionality
The functionality of the laptop that is tested and working is precisely described in the document "Checklist". 
underneath here you will find a general overview of what needs to be fixed, and also what is and what is not working.
// i lost the file somewhere on my laptop, will upload if i find it again!😓

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
- [x] Intel WIFI
- [ ] Intel Bluetooth
- [ ] Airdrop
- [ ] Handoff
- [ ] Sidecar

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
- [ ] Filefautling
- [x] System Intergrity Protection
- [x] Multibooting
- [ ] Keyboard shortcuts 

## What needs to be fixed (Issues)

- [ ] Type-c-to-HDMI dongle
- [ ] trackpad buttons non-functional
- [x] "NON-HP battery" warning
- [x] Battery percentage Readout freeze
- [x] Battery not charging sometimes
- [ ] wake laptop by keyboard
- [ ] Can't turn on keyboard backlighting
- [ ] replace wifi card with broadcom

### Optional
- [ ] replace Intel wifi card with Broadcom
- [x] Buy Type-c-to-HDMI dongle
- [ ] Enable Bootchime
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
- using propertree en gensmbios, fill in the missing smbios details
- boot your hp omen into bios and put in the appropriate settings
- boot opencore from the usb and install macos using the installer
- after installation, mount the efi partition of the macos hard drive and usb and copy the efi from the usb onto the hard drive
- ready and done. unplug, reboot and stash that usb somewhere!

# references
🫥
https://dortania.github.io/OpenCore-Install-Guide/
