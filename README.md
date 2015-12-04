You will find the precompiled version of the x86 toolchain from the TD-W8970 GPL tarball at the [releases section](https://github.com/mkresin/u-boot/releases).

```shell
export PATH=/your/path/to/toolchain-mips_r2_gcc-4.3.3+cs_uClibc-0.9.30.1_2_6_32/usr/bin/:$PATH
export ARCH=mips
export CROSS_COMPILE=mips-linux-

make distclean vr9_config
cp tdw8970.config .config
make oldconfig u-boot.lq u-boot.asc
```

After compiling, you will find the following files in your directory:

- u-boot.asc: UART u-boot (allows booting via serial console) 
- u-boot.lq: u-boot that can be written to flash

Please note that in case of an UART boot, the CPU will only run at 125MHz. So don't expect it to be as fast as usual.
