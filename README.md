# Xiaomi-R3-OpenWrt-Stable
**All Xiaomi-R3 codes** are from [X-Wrt](https://github.com/x-wrt/x-wrt) project  
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

## Which files were changed?
The following is a list of major modified files.
```
/package/boot/uboot-envtools/files/ramips
/target/linux/ramips/dts/mt7620a_xiaomi_miwifi-r3.dts
/target/linux/ramips/image/mt7620.mk
/target/linux/ramips/mt7620/base-files/etc/board.d/02_network
/target/linux/ramips/mt7620/base-files/lib/upgrade/platform.sh
/target/linux/ramips/mt7620/config-5.4
/target/linux/ramips/mt7620/target.mk
/target/linux/ramips/patches-5.4/0038-mtd-ralink-add-mt7620-nand-driver.patch
```

## Which packages were added?
```
Target System
	- MediaTek Ralink MIPS

Subtarget
	- MT7620 based boards

Target Profile
	- Xiaomi Mi Router R3

Base system
	- block-mount
	- ca-certificates

Kernel modules
	- Filesystems
		- kmod-fs-exfat
		- kmod-fs-ntfs
		- kmod-fs-vfat
	- Native Language Support
		- kmod-nls-cp936
	- Other modules
		- kmod-mtd-rw
	- USB Support
		- kmod-usb-storage
		- kmod-usb-uhci

LuCI
	- Collections
		- luci
```

## How to use this build action?
1. Putting you git patches under the '/patches' folder.
2. Changing default config file by replacing new '/.config' file.
3. Adding custom files by creating '/files' folder. It will be moved to 'openwrt/files/'.
4. Changing default 'feeds.conf.default' file by adding new '/feeds.conf.default' file.
5. The branch that needs to be compiled can be specified by modifying REPO_BRANCH under the env block in /.github/workflows/build-openwrt.yml.

**Warning:   
This code only contains the adaptation to the 5.4 kernel.  
If you need to compile the snapshot or newer version of the code, you need to adapt to the 5.10 kernel.**

## Luci
- Wifi SSID: OpenWrt  
- Gateway: 192.168.1.1  
- User: root  
- Password: password  

## Thanks project
[OpenWrt](https://github.com/openwrt/openwrt)  
[X-Wrt](https://github.com/x-wrt/x-wrt)  
[Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt)  
