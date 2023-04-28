ZynqMP-FPGA-Debian11
====================================================================================

Overview
------------------------------------------------------------------------------------

### Introduction

This Repository provides a Linux Boot Image(U-boot, Kernel, Debian 11 RootFS) for Zynq MPSoC.

### Note

**The Linux Kernel Image and Debian11 RootFS provided in this repository is not official.**

**I modified it to my liking. Please handle with care.**


### Features

* Hardware
  + UltraZed-EG-IOCC : Xilinx Zynq UltraScale+ MPSoC Starter Kit by Avnet.
  + Ultra96    : Xilinx Zynq UltraScale+ MPSoC development board based on the Linaro 96Boards specification. 
  + Ultra96-V2 : updates and refreshes the Ultra96 product that was released in 2018.
  + KV260      : Kria KV260 Vision AI Startar Kit.
* Boot Loader
  + FSBL(First Stage Boot Loader for ZynqMP)
  + PMU Firmware(Platform Management Unit Firmware)
  + BL31(ARM Trusted Firmware Boot Loader stage 3-1)
  + U-Boot xilinx-v2019.2 (customized)
* Linux Kernel Version 5.15.108-zynqmp-fpga-generic
  + [linux-stable 5.15.108](https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux.git//tag/?h=v5.15.108)
  + Patched equivalent to linux-xlnx v2022.2
  + Enable Device Tree Overlay with Configuration File System
  + Enable FPGA Manager
  + Enable FPGA Bridge
  + Enable FPGA Reagion
  + Enable ATWILC3000 Linux Driver for Ultra96-V2
* Debian11.1(bullseye) Root File System
  + Installed build-essential
  + Installed device-tree-compiler
  + Installed ruby ruby-msgpack ruby-serialport
  + Installed python python3 msgpack-rpc-python
  + Installed u-boot-tools
  + Installed Other package list -> [files/debian11-dpkg-list.txt](files/debian11-dpkg-list.txt)
* FPGA Device Drivers and Services
  + [fclkcfg    (FPGA Clock Configuration Device Driver)](https://github.com/ikwzm/fclkcfg)
  + [u-dma-buf  (User space mappable DMA Buffer)](https://github.com/ikwzm/udmabuf)

Release
------------------------------------------------------------------------------------

The main branch contains only Readme.md.     
For Linux Kernel and Debian11 RootFS, please refer to the respective release tag listed below.

| Release  | Released  | Debian Version | Linux Kernel Version           | Release Tag |
|:---------|:----------|:---------------|:-------------------------------|:------------|
| v0.1.2   | 2023-4-29 | Debian 11.6    | 5.15.108-zynqmp-fpga-generic-3 | [v0.1.2](https://github.com/ikwzm/ZynqMP-FPGA-Debian11/tree/v0.1.2)

Install
------------------------------------------------------------------------------------

* Install Boot Loader and Linux to SD-Card
  + [UltraZed-EG-IOCC](doc/install/ultrazed-eg-iocc.md)
  + [Ultra96](doc/install/ultra96.md)
  + [Ultra96-V2](doc/install/ultra96v2.md)
  + [KV260](doc/install/kv260.md)

Other Projects
------------------------------------------------------------------------------------

* https://github.com/ikwzm/ZynqMP-FPGA-Linux-Kernel-5.15
  + Linux Kernel (v5.15.x) Image and Device Trees for Zynq MPSoC.
* https://github.com/ikwzm/ZynqMP-FPGA-Ubuntu22.04-Console
  + Linux Boot Image(U-boot, Kernel, Ubuntu 22.04-Console) for Ultra96/Ultra96-V2/Kv260
* https://github.com/ikwzm/ZynqMP-FPGA-Ubuntu22.04-Desktop
  + Linux Boot Image(U-boot, Kernel, Ubuntu 22.04-Desktop) for Ultra96/Ultra96-V2/Kv260
* https://github.com/ikwzm/ZynqMP-FPGA-Xserver
  + The X-Window server Debian Package for ZynqMP-FPGA-Linux
* https://github.com/ikwzm/ZynqMP-FPGA-XRT
  + The XRT(Xilinx Runtime) Debian Package for ZynqMP-FPGA-Linux


Examples
------------------------------------------------------------------------------------

* https://github.com/ikwzm/ArgSort-Kv260
  + ArgSort for Kv260
* https://github.com/ikwzm/ArgSort-Ultra96
  + ArgSort for Ultra96/Ultra96-V2
* https://github.com/ikwzm/ZynqMP-FPGA-Linux-Example-2-Ultra96
  + ZynqMP-FPGA-Linux Example (2) binary and test code for Ultra96
* https://github.com/ikwzm/ZynqMP-FPGA-Linux-Example-0-UltraZed
  + ZynqMP-FPGA-Linux Example (0) binary and test code for UltraZed-EG-IOCC
* https://github.com/ikwzm/ZynqMP-FPGA-Linux-Example-2-UltraZed
  + ZynqMP-FPGA-Linux Example (2) binary and test code for UltraZed-EG-IOCC
* https://github.com/ikwzm/ZynqMP-FPGA-Linux-Example-3-UltraZed
  + ZynqMP-FPGA-Linux Example (3) binary and test code for UltraZed-EG-IOCC
