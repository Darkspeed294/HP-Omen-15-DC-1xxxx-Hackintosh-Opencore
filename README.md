# HP-Omen-15-DC-1xxxx-Hackintosh-Opencore

This project is dedicated to Opencore development on the HP Omen 15 DC-10008UA. In general this hackintosh project works on all HP Omen 15 DC-1xxxxx laptops with a UHD 630 and a proper SSD (original one does not work probably, check yours as it might differ from factory).
<video width="320" height="240" autoplay loop muted>
  <source src="https://github.com/Darkspeed294/HP-Omen-15-DC-1xxxx-Hackintosh-Opencore/assets/84881650/6f41a841-6626-4367-a8cd-06c35237a83d)" type="video/Webm" />
  Your browser does not support the video tag.
</video>
# Installation instructions
> This installation method only works on MacOS. See Dortania's Opencore guide for different Operating system installation methods!
- Download my EFI from the 'realease' channel.
- Download an up-to-date MacOS installer by pasting the following lines one by one in to the terminal
  ```
  curl https://bootstrap.pypa.io/get-pip.py
  -o get-pip.py python3 get-pip.py
  mkdir -p ~/macOS-installer && cd ~/macOS-installer && curl https://raw.githubusercontent.com/munki/macadmin-scripts/main/installinstallmacos.py > installinstallmacos.py && sudo python3 installinstallmacos.py
  ```
- Format USB drive as MyVolume (MacOS extended) using Disk Utility
- Make the USB drive bootable
  ```
  sudo /Applications/Install\ macOS\ Sonoma.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume
  ```
- Mount the efi partition of the usb stick with [mountefi tool](https://github.com/corpnewt/MountEFI)
- Download and drop the efi folder of mine onto your usb stick
- Using [Propertree](https://github.com/corpnewt/ProperTree) and [gensmbios](https://github.com/corpnewt/GenSMBIOS), fill in the missing smbios details
- Boot your hp omen into bios and put in [the appropriate settings](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake-plus.html#intel-bios-settings)
- Boot opencore from the usb and install macos using the installer
- After installation, mount the efi partition of the macos hard drive and usb and copy the efi from the usb onto the hard drive
- Ready and done. unplug, reboot and stash that backup dummy usb somewhere!

  
# Screenshots
<details>
<summary>Ventura 13.6</summary>
<picture>
  <img src="https://user-images.githubusercontent.com/84881650/173489275-d11a2264-73df-493c-99b0-b4214e23a390.jpeg" alt="Ventura" style="width:500px;height:600px;">
</picture>
<picture>
  <img src="https://user-images.githubusercontent.com/84881650/173489862-65fb6e78-cfee-4d56-8203-c84596c8b739.png" alt="Ventura" style="width:500px;height:600px;">
</picture>
<picture>
  <img src="https://user-images.githubusercontent.com/84881650/173489944-e32961d0-0837-4961-8d45-5c23dd7ecea7.png" alt="Ventura" style="width:500px;height:600px;">
</picture>
<picture>
  <img src="https://user-images.githubusercontent.com/84881650/173489867-583de278-32a9-4345-8fff-6988a80b878b.png" alt="Ventura" style="width:500px;height:600px;">
</picture>
<picture>
  <img src="https://user-images.githubusercontent.com/84881650/173489891-49daaa1c-a5bf-44ec-9a77-a76a5ec20344.jpeg" alt="Ventura" style="width:500px;height:600px;">
</picture>
<picture>
  <img src="https://user-images.githubusercontent.com/84881650/180302364-be0c7a2d-2448-45d7-b06d-de74bb020d7d.jpeg" alt="Ventura" style="width:500px;height:600px;">
</picture>
<picture>
  <img src="https://user-images.githubusercontent.com/84881650/180302389-261ea264-b55c-4b0e-a165-48f405692024.jpeg" alt="Ventura" style="width:500px;height:600px;">
</picture>
</details>    


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
| SSD     | Samsung SSD 870 EVO Series (1TB) | 
| Display | 1080p IPS generic shit |
| Ethernet| Realtek RTL8111|
| Wireless| Broadcom BCM94360CS2 |
| Chipset | HM370 |

### peripherals   

| device type  | Description |
| :-: | :-: |
| pointer | SYN327C |
| keyboard| PNP0303 |
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
|Opencore version | 0.9.8 commit |
|MacOS version| 14.2 Sonoma |
|Bios version |F.24 Rev.A|
|Audio Codec |Realtek ALC295|

# Functionality

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
- [x] Trackpad
- [x] Keyboard
- [x] Webcam
- [x] USB
- [x] Type-C 

### Services
- [x] Filefaulting
- [x] System Intergrity Protection (Sonoma and broadcom requires this off)
- [x] Multibooting
- [x] Keyboard shortcuts 

## What needs to be fixed (Issues)

- [x] Type-c-to-HDMI dongle
- [x] trackpad buttons non-functional
- [x] "NON-HP battery" warning
- [x] Battery percentage Readout freeze
- [x] Battery not charging sometimes
- [-] wake laptop by keyboard (power button works)
- [ ] Can't turn on keyboard backlighting 
- [x] replace wifi card with broadcom

### Optional
- [x] replace Intel wifi card with Broadcom
- [x] Buy Type-c-to-HDMI dongle
- [x] Enable Bootchime
- [x] Fix RTC timezone difference between windows and MacOS (can be fixed in windows)


## What will never work
| What  | Why |
| :-: | :-: |
| dGPU | Apple dropped support for Nvidia webdrivers since High Sierra. Besides there were never MacOS drivers for the gtx 16-series.|
| HDMI | The built-in HDMI port on this laptop is linked to dGPU. Unfortunately, there are no drivers and the dGPU is disabled.|
|Airdrop| Airdrop and Handoff are not supported on Intel wifi chips. For this, a Broadcom wifi chip needs to be acquired.|



# references
🫥
https://dortania.github.io/OpenCore-Install-Guide/
