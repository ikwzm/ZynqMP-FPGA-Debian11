## UltraZed EG IOCC

### Downlowd from github

**Note: Downloading the entire repository takes time, so download the source code from https://github.com/ikwzm/ZynqMP-FPGA-Debian11/releases.**

```console
shell$ wget https://github.com/ikwzm/ZynqMP-FPGA-Debian11/archive/refs/tags/v1.0.0.tar.gz
shell$ tar xfz v1.0.0.tar.gz
shell$ cd ZynqMP-FPGA-Debian11-1.0.0
```

### File Description

 * target/UltraZed-EG-IOCC/
   + boot/
     - boot.bin                                                 : Stage 1 Boot Loader
     - uEnv.txt                                                 : U-Boot environment variables for linux boot
     - devicetree-5.15.108-zynqmp-fpga-generic-uz3eg-iocc.dtb   : Linux Device Tree Blob   
     - devicetree-5.15.108-zynqmp-fpga-generic-uz3eg-iocc.dts   : Linux Device Tree Source
 * files/
     - vmlinuz-5.15.108-zynqmp-fpga-generic-5                   : Linux Kernel Image
 * debian11-rootfs-vanilla.tgz.files/                           : Debian11 Root File System
   + x00 .. x08                                                 : (splited files)
 * debian/
   - linux-image-5.15.108-zynqmp-fpga-generic_5.15.108-zynqmp-fpga-generic-5_arm64.deb   : Linux Image Package
   - linux-headers-5.15.108-zynqmp-fpga-generic_5.15.108-zynqmp-fpga-generic-5_arm64.deb : Linux Headers Package
   - fclkcfg-5.15.108-zynqmp-fpga-generic_1.7.2-1_arm64.deb     : fclkcfg(1.7.2) Device Driver and Services Package
   - u-dma-buf-5.15.108-zynqmp-fpga-generic_4.4.1-0_arm64.deb   : u-dma-buf(4.4.1) Device Driver and Services Package
 
### Format SD-Card

[./doc/install/format-disk.md](format-disk.md)

### Write to SD-Card

#### Mount SD-Card

```console
shell# mount /dev/sdc1 /mnt/usb1
shell# mount /dev/sdc2 /mnt/usb2
```
#### Make Boot Partition

```console
shell# cp target/UltraZed-EG-IOCC/boot/*                         /mnt/usb1
shell# gzip -d -c files/vmlinuz-5.15.108-zynqmp-fpga-generic-5 > /mnt/usb1/image-5.15.108-zynqmp-fpga-generic
```

#### Make RootFS Partition

```console
shell# cat debian11-rootfs-vanilla.tgz.files/* | tar xfz - -C /mnt/usb2
shell# mkdir                                                  /mnt/usb2/home/fpga/debian
shell# cp debian/*                                            /mnt/usb2/home/fpga/debian
```

#### Add boot partition mount position to /etc/fstab

```console
shell# mkdir /mnt/usb2/mnt/boot
shell# cat <<EOT >> /mnt/usb2/etc/fstab
/dev/mmcblk1p1	/mnt/boot	auto	defaults	0	0
EOT
```

#### Unmount SD-Card

```console
shell# umount /mnt/usb1
shell# umount /mnt/usb2
```

### Install Debian Packages

[./doc/install/debian-packages.md](debian-packages.md.md)
