### Install Debian Packages

#### Boot Target Board and login fpga or root user

fpga'password is "fpga".

```console
debian-fpga login: fpga
Password:
fpga@debian-fpga:~$
```

root'password is "admin".

```console
debian-fpga login: root
Password:
root@debian-fpga:~#
```

#### Install Linux Image Package

Since linux-image-5.15.108-zynqmp-fpga-generic_5.15.108-zynqmp-fpga-generic-5_arm64.deb is already pre-installed in debian11-rootfs.tgz, this The process can be omitted.

```console
root@debian-fpga:~# cd /home/fpga/debian
root@debian-fpga:/home/fpga/debian# dpkg -i linux-image-5.15.108-zynqmp-fpga-generic_5.15.108-zynqmp-fpga-generic-5_arm64.deb
(Reading database ... 27341 files and directories currently installed.)
Preparing to unpack linux-image-5.15.108-zynqmp-fpga-generic_5.15.108-zynqmp-fpga-generic-5_arm64.deb ...
Unpacking linux-image-5.15.108-zynqmp-fpga-generic (5.15.108-zynqmp-fpga-generic-5) over (5.15.108-zynqmp-fpga-generic-5) ...
Setting up linux-image-5.15.108-zynqmp-fpga-generic (5.15.108-zynqmp-fpga-generic-5) ...
```

#### Install Linux Headers Package

```console
root@debian-fpga:~# cd /home/fpga/debian
root@debian-fpga:/home/fpga/debian# dpkg -i linux-headers-5.15.108-zynqmp-fpga-generic_5.15.108-zynqmp-fpga-generic-5_arm64.deb
Selecting previously unselected package linux-headers-5.15.108-zynqmp-fpga-generic.
(Reading database ... 27341 files and directories currently installed.)
Preparing to unpack linux-headers-5.15.108-zynqmp-fpga-generic_5.15.108-zynqmp-fpga-generic-5_arm64.deb ...
Unpacking linux-headers-5.15.108-zynqmp-fpga-generic (5.15.108-zynqmp-fpga-generic-5) ...
Setting up linux-headers-5.15.108-zynqmp-fpga-generic (5.15.108-zynqmp-fpga-generic-5) ...
make: Entering directory '/usr/src/linux-headers-5.15.108-zynqmp-fpga-generic'
  SYNC    include/config/auto.conf.cmd
  HOSTCC  scripts/basic/fixdep
  HOSTCC  scripts/kconfig/conf.o
  HOSTCC  scripts/kconfig/confdata.o
  HOSTCC  scripts/kconfig/expr.o
  LEX     scripts/kconfig/lexer.lex.c
  YACC    scripts/kconfig/parser.tab.[ch]
  HOSTCC  scripts/kconfig/lexer.lex.o
  HOSTCC  scripts/kconfig/menu.o
  HOSTCC  scripts/kconfig/parser.tab.o
  HOSTCC  scripts/kconfig/preprocess.o
  HOSTCC  scripts/kconfig/symbol.o
  HOSTCC  scripts/kconfig/util.o
  HOSTLD  scripts/kconfig/conf
*
* Restart config...
*
*
* ARMv8.5 architectural features
*
Branch Target Identification support (ARM64_BTI) [Y/n/?] y
Enable support for E0PD (ARM64_E0PD) [Y/n/?] y
Enable support for random number generation (ARCH_RANDOM) [Y/n/?] y
Memory Tagging Extension support (ARM64_MTE) [Y/n/?] (NEW)
*
* KASAN: runtime memory debugger
*
KASAN: runtime memory debugger (KASAN) [N/y/?] (NEW)
  HOSTCC  scripts/dtc/dtc.o
  HOSTCC  scripts/dtc/flattree.o
  HOSTCC  scripts/dtc/fstree.o
  HOSTCC  scripts/dtc/data.o
  HOSTCC  scripts/dtc/livetree.o
  HOSTCC  scripts/dtc/treesource.o
  HOSTCC  scripts/dtc/srcpos.o
  HOSTCC  scripts/dtc/checks.o
  HOSTCC  scripts/dtc/util.o
  HOSTCC  scripts/dtc/dtc-lexer.lex.o
  HOSTCC  scripts/dtc/dtc-parser.tab.o
  HOSTLD  scripts/dtc/dtc
  HOSTCC  scripts/dtc/libfdt/fdt.o
  HOSTCC  scripts/dtc/libfdt/fdt_ro.o
  HOSTCC  scripts/dtc/libfdt/fdt_wip.o
  HOSTCC  scripts/dtc/libfdt/fdt_sw.o
  HOSTCC  scripts/dtc/libfdt/fdt_rw.o
  HOSTCC  scripts/dtc/libfdt/fdt_strerror.o
  HOSTCC  scripts/dtc/libfdt/fdt_empty_tree.o
  HOSTCC  scripts/dtc/libfdt/fdt_addresses.o
  HOSTCC  scripts/dtc/libfdt/fdt_overlay.o
  HOSTCC  scripts/dtc/fdtoverlay.o
  HOSTLD  scripts/dtc/fdtoverlay
  HOSTCC  scripts/selinux/genheaders/genheaders
  HOSTCC  scripts/selinux/mdp/mdp
  HOSTCC  scripts/kallsyms
  HOSTCC  scripts/sorttable
  HOSTCC  scripts/asn1_compiler
  HOSTCC  scripts/extract-cert
  CC      scripts/mod/empty.o
  HOSTCC  scripts/mod/mk_elfconfig
  MKELF   scripts/mod/elfconfig.h
  CC      scripts/mod/devicetable-offsets.s
  HOSTCC  scripts/mod/modpost.o
  HOSTCC  scripts/mod/file2alias.o
  HOSTCC  scripts/mod/sumversion.o
  HOSTLD  scripts/mod/modpost
scripts/Makefile.build:459: warning: overriding recipe for target 'modules.order'
Makefile:1508: warning: ignoring old recipe for target 'modules.order'
make: Leaving directory '/usr/src/linux-headers-5.15.108-zynqmp-fpga-generic'
```

#### Install fclkcfg Device Driver and Services Package

```console
root@debian-fpga:~# cd /home/fpga/debian
root@debian-fpga:/home/fpga/debian# dpkg -i fclkcfg-5.15.108-zynqmp-fpga-generic_1.7.2-1_arm64.deb
Selecting previously unselected package fclkcfg-5.15.108-zynqmp-fpga-generic.
(Reading database ... 43883 files and directories currently installed.)
Preparing to unpack fclkcfg-5.15.108-zynqmp-fpga-generic_1.7.2-1_arm64.deb ...
Unpacking fclkcfg-5.15.108-zynqmp-fpga-generic (1.7.2-1) ...
Setting up fclkcfg-5.15.108-zynqmp-fpga-generic (1.7.2-1) ...
```

#### Install u-dma-buf Device Driver and Services Package

```console
root@debian-fpga:~# cd /home/fpga/debian
root@debian-fpga:/home/fpga/debian# dpkg -i u-dma-buf-5.15.108-zynqmp-fpga-generic_4.4.1-0_arm64.deb
Selecting previously unselected package u-dma-buf-5.15.108-zynqmp-fpga-generic.
(Reading database ... 43889 files and directories currently installed.)
Preparing to unpack u-dma-buf-5.15.108-zynqmp-fpga-generic_4.4.1-0_arm64.deb ...
Unpacking u-dma-buf-5.15.108-zynqmp-fpga-generic (4.4.1-0) ...
Setting up u-dma-buf-5.15.108-zynqmp-fpga-generic (4.4.1-0) ...
```

