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

| Part  | Description |
| :-: | :-: |
|Opencore version | 0.7.8 |
|MacOS version| 12.2.1 |
|Bios version |F.23 Rev.A|
|Audio Codec |Realtek ALC295|

# Functionality
The functionality of the laptop that is tested and working is precisely described in the document "Checklist". 
underneath here you will find a general overview of what needs to be fixed, and also what is and what is not working.

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
- [ ] Battery readout
- [ ] Battery charging

### Wireless
- [x] Intel WIFI
- [x] Intel Bluetooth
- [ ] Airdrop
- [ ] Handoff
- [ ] Sidecar

### Disk
- [x] NVME working
- [x] SSD working
- [x] NVRAM
- [ ] Trim support

### Peripherals
- [ ] Trackpad
- [ ] Keyboard
- [ ] Webcam
- [ ] USB
- [ ] Type-C

### Services
- [ ] Filefautling
- [ ] System Intergrity Protection
- [ ] Multibooting
- [ ] Keyboard shortcuts 

## What needs to be fixed (Issues)
- wake by keyboard
- Type-c to HDMI dongle
- trackpad buttons not working

## What will never work
| What  | Why |
| :-: | :-: |
| dGPU | Apple dropped support for Nvidia webdrivers since High Sierra. Besides there were never MacOS drivers for the gtx 16-series.|
| HDMI | The built-in HDMI port on this laptop is linked to dGPU. Unfortunately, there are no drivers and the dGPU is disabled.

# Installation instructions
# references
https://github.com/0xFireWolf/RealtekCardReader
