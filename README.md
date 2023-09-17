# Opencore HP 250 G7 - macOS Monterey

Opencore config for my laptop.
Current OC version: 0.9.5
Current tested macOS version: 12.6.7

### Hardware
- CPU: i5-8350u
- RAM: 8GB
- SSD: WDC 250GB SSD
- GPU: Intel UHD 620
- Ethernet: Realtek Ethernet 10/100/1000 GbE
- Audio: Realtek ALC236 (layout 3, 11, 12, 13, 14, 15, 16, 17, 18, 23, 36, 54, 99)
- WiFi & Bluetooth: Realtek 802.11ac (2x2) Wi-Fi and Bluetooth 5.0 Combo (UNSUPPORTED)
- Synaptics Trackpad (SMBus)

### Benchmarks
- [Geekbench 5 CPU](https://browser.geekbench.com/v5/cpu/21198717)
- [Geekbench 5 GPU Metal](https://browser.geekbench.com/v5/compute/6536180)
- [Geekbench 5 GPU OpenCL](https://browser.geekbench.com/v5/compute/6536178)

### Installation
1. Download the latest release
2. Download propertree and edit EFI/OC/config.plist
    1. Change PlatformInfo -> MLB, ROM, SystemUUID and SystemSerialNumber using [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
3. Create the macOS Installer USB-Stick using [this](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) guide. You don't need to create the EFI, that work have I done already. 
4. Update the BIOS settings according to [this](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake.html#intel-bios-settings) guide. 
5. Insert USB and boot! When entering the macOS Recovery, click Disk Utility, format your Disk as APFS/GUID and then install macOS.

### Working
- iServices
- Davinci Resolve
- Audio
- GPU Acceleration
- USB Ports
- SD Reader
- DVD Drive
- SSD Drive, run `sudo trimforce enable` after installation to ensure no problems appear
- HDMI
- Webcam
- Shutdown and Restart
- Sleep, run following commands after installation:
```
    sudo pmset autopoweroff 0
    sudo pmset powernap 0
    sudo pmset standby 0
    sudo pmset proximitywake 0
    sudo pmset tcpkeepalive 0
```
- CPU temp
- Xcode
- Trackpad gestures


### Not working
- WiFi and Bluetooth natively, you have to buy a BCM94360NG replacement
- Fan control

### Bugs
- <strike>No SATA controller</strike>
