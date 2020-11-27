------



# 一 Yocto



## Yocto 

### 1.1.1 Yocto SDK的编译
	
	cd apps_proc/
	
	source poky/build/conf/set_bb_env.sh
	
	buildconfig RG500QEA_VH RG500QEAR10A01M4G STD YP
	
	build-sdxprairie-image
	
### 1.1.1 烧录

目标文件中的关键文件

	pp bootloader			apps_proc/bootable/bootloader/edk2	abl.elf
	Linux kernel image		apps_proc/kernel			sdxprairie-boot.img
	Recovery root file system	apps_proc/OTA/recovery			sdxprairie-recoveryfs.ubi
	Root file system		除上述目录外的其他所有目录		sdxprairie-sysfs.ubi
	
Windows QFlash 烧录失败。

Fastboot 烧录

	adb reboot bootloader
	fastboot flash boot sdxprairie-boot.img
	fasboot flash system sdxprairie-sysfs.ubi
	fasboot flash bootloader abl.elf

## Kernel Driver

### emmc / sd 卡驱动

 

