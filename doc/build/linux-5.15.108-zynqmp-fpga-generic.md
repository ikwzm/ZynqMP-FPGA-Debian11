## Build Linux 5.10.120-zynqmp-fpga-trial

### Download ZynqMP-FPGA-Linux-Kernel-5.15

```console
shell$ wget https://github.com/ikwzm/ZynqMP-FPGA-Linux-Kernel-5.15/archive/refs/tags/5.15.108-zynqmp-fpga-generic-1.tar.gz
shell$ tar xfz 5.15.108-zynqmp-fpga-generic-1.tar.gz
```

### Copy Linux Kernel Image to this repository

```console
shell$ cp ZynqMP-FPGA-Linux-Kernel-5.15-5.15.108-zynqmp-fpga-generic-1/vmlinuz-5.15.108-zynqmp-fpga-generic-1      ./files
shell$ cp ZynqMP-FPGA-Linux-Kernel-5.15-5.15.108-zynqmp-fpga-generic-1/files/config-5.15.108-zynqmp-fpga-generic-1 ./files
```

### Copy Linux Image and Header Debian Packages to this repository

```console
shell$ cp ZynqMP-FPGA-Linux-Kernel-5.15-5.15.108-zynqmp-fpga-generic-1/linux-image-5.15.108-zynqmp-fpga-generic_5.15.108-zynqmp-fpga-generic-1_arm64.deb ./debian/
shell$ cp ZynqMP-FPGA-Linux-Kernel-5.15-5.15.108-zynqmp-fpga-generic-1/linux-headers-5.15.108-zynqmp-fpga-generic_5.15.108-zynqmp-fpga-generic-1_arm64.deb ./debian/
```

### Copy devicetree for KV260

```console
shell$ install -d target/Kv260/boot/
shell$ cp ZynqMP-FPGA-Linux-Kernel-5.15-5.15.108-zynqmp-fpga-generic-1/devicetrees/5.15.108-zynqmp-fpga-generic-1/zynqmp-kv260-revB.dtb ./target/Kv260/boot/devicetree-5.15.108-zynqmp-fpga-generic-kv260-revB.dtb
shell$ dtc -I dtb -O dts --symbols -o ./target/Kv260/boot//devicetree-5.15.108-zynqmp-fpga-generic-kv260-revB.dts ./target/Kv260/boot//devicetree-5.15.108-zynqmp-fpga-generic-kv260-revB.dtb
```

### Copy devicetree for KR260

```console
shell$ install -d target/Kr260/boot/
shell$ cp ZynqMP-FPGA-Linux-Kernel-5.15-5.15.108-zynqmp-fpga-generic-1/devicetrees/5.15.108-zynqmp-fpga-generic-1/zynqmp-kr260-revB.dtb ./target/Kr260/boot/devicetree-5.15.108-zynqmp-fpga-generic-kr260-revB.dtb
shell$ dtc -I dtb -O dts --symbols -o ./target/Kr260/boot/devicetree-5.15.108-zynqmp-fpga-generic-kr260-revB.dts ./target/Kr260/boot/devicetree-5.15.108-zynqmp-fpga-generic-kr260-revB.dtb
```

### Copy devicetree for Ultra96

```console
shell$ install -d target/Ultra96/boot/
shell$ cp ZynqMP-FPGA-Linux-Kernel-5.15-5.15.108-zynqmp-fpga-generic-1/devicetrees/5.15.108-zynqmp-fpga-generic-1/avnet-ultra96-rev1.dtb ./target/Ultra96/boot/devicetree-5.15.108-zynqmp-fpga-generic-ultra96.dtb
shell$ dtc -I dtb -O dts --symbols -o ./target/Ultra96/boot/devicetree-5.15.108-zynqmp-fpga-generic-ultra96.dts ./target/Ultra96/boot/devicetree-5.15.108-zynqmp-fpga-generic-ultra96.dtb
```

### Copy devicetree for Ultra96-V2

```console
shell$ install -d target/Ultra96-V2/boot/
shell$ cp ZynqMP-FPGA-Linux-Kernel-5.15-5.15.108-zynqmp-fpga-generic-1/devicetrees/5.15.108-zynqmp-fpga-generic-1/avnet-ultra96v2-rev1.dtb ./target/Ultra96-V2/boot/devicetree-5.15.108-zynqmp-fpga-generic-ultra96v2.dtb
shell$ dtc -I dtb -O dts --symbols -o ./target/Ultra96-V2/boot/devicetree-5.15.108-zynqmp-fpga-generic-ultra96v2.dts ./target/Ultra96-V2/boot/devicetree-5.15.108-zynqmp-fpga-generic-ultra96v2.dtb
```

### Copy devicetree for UltraZed-EG-IOCC

```console
shell$ install -d target/UltraZed-EG-IOCC/boot/
shell$ cp ZynqMP-FPGA-Linux-Kernel-5.15-5.15.108-zynqmp-fpga-generic-1/devicetrees/5.15.108-zynqmp-fpga-generic-1/zynqmp-uz3eg-iocc.dtb ./target/UltraZed-EG-IOCC/boot/devicetree-5.15.108-zynqmp-fpga-generic-uz3eg-iocc.dtb
shell$ dtc -I dtb -O dts --symbols -o ./target/UltraZed-EG-IOCC/boot/devicetree-5.15.108-zynqmp-fpga-generic-uz3eg-iocc.dts ./target/UltraZed-EG-IOCC/boot/devicetree-5.15.108-zynqmp-fpga-generic-uz3eg-iocc.dtb
```

