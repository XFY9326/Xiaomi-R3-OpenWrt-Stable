# Xiaomi-R3-OpenWrt-Stable
All Xiaomi-R3 codes are from [X-Wrt](https://github.com/x-wrt/x-wrt) project  
This build action will also upload firmware that supports pbboot (PandoraBox)

## OpenWrt version
Current stable target is openwrt-21.02.0

## Feature
- Original OpenWrt
- Add original luci interface by default
- Add USB storage support (Support NTFS, FAT, FAT32, EXFAT by default)
- Enable wifi by default

## How to use
**Recommended**
1. Flash pbboot first
2. Open pbboot web page and flash firmware that end with '-pbboot.bin'
3. Enjoy it

Or you can use any way that can flash OpenWrt firmware.

## Luci
- Wifi SSID: OpenWrt  
- Gateway: 192.168.1.1  
- User: root  
- Password: password  

## Thanks project
[OpenWrt](https://github.com/openwrt/openwrt)  
[X-Wrt](https://github.com/x-wrt/x-wrt)  
[Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt)  
