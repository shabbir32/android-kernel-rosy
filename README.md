# Clean 3.18 CAF kernel for Xiaomi Redmi 5

Completely clean and minimal kernel base (bare-metal kernel) with everything working.

## About phone

![phone](rosy.jpg)

##### Basic specifications:
```
Codename - rosy
SoC - Snapdragon 450
CPU - Octa-core 1.8 GHz Cortex-A53
GPU - 600 MHz Adreno 506
```

Full specifications - [GSM Arena](https://www.gsmarena.com/xiaomi_redmi_5-8768.php)

## Features & information

##### Main features:
```
* Clean, optimized, and minimal imports of code for rosy (based on riva-o-oss branch).
* Optimized touchscreen drivers (fixed freezing and reduced debugging).
* Can be compiled with GCC 9.2.0, all code warnings are fixed.
* Compiler tuned for Cortex-A53 (CPU optimization).
* Full F2FS support.
* Miscellaneous config improvements that are not listed here.
```

##### Information:
```
- CPU governors: [interactive], conservative, ondemand, userspace, powersave, performance.
- I/O schedulers: [cfq], noop, deadline.
- TCP algorithms: [westwood], cubic, reno.
- Compression algorithms: [lz4], lzo.
```

## Branches

##### master:
```
- Default branch with all other branches merged.
```

##### 3.18-fixes:
```
- Contains commits that fix various things.
```

##### 3.18-gcc-fixes:
```
- Contains commits that fix various things by/for GCC.
```

##### 3.18-optimizations:
```
- Contains commits for optimization mostly specific to rosy.
```

##### 3.18-rosy-o:
```
- Contains buildable oreo kernel base for rosy (but needs 3.18-fixes branch merged).
```

##### 3.18-upstream:
```
- Contains linux-3.18.y branch's commits of linux-stable and f2fs-stable repositories.
```

##### LA.UM.8.6.r1-03400-89xx.0:
```
- CAF tag LA.UM.8.6.r1-03400-89xx.0 (January 29, 2019; Linux 3.18.124).
```

## Cloning & building

This kernel contains submodules. To build it successfully, you have to either clone it with `--recursive` option or do `git submodule update --init --recursive` in the kernel directory after cloning.

Make sure you are building the kernel with `rosy-perf_defconfig`. In case you want to base on another defconfig, you can easily enable ROSY's drivers in any config using the kernel's `menuconfig`. You can find a special section with drivers for ROSY in `menuconfig > Device Drivers > Drivers for ROSY`. Do not forget to build the Wi-Fi (prima) drivers though, they are located in `menuconfig > Device Drivers > Staging drivers`.

##### Steps (normal defconfig):
```
1 - make ARCH=arm64 <defconfig>
2 - make ARCH=arm64 menuconfig
3 - make ARCH=arm64 savedefconfig
4 - mv defconfig arch/arm64/configs/menuconfig_defconfig
```

##### Steps (raw defconfig):
```
1 - make ARCH=arm64 <defconfig>
2 - make ARCH=arm64 menuconfig
3 - mv .config arch/arm64/configs/menuconfig_rawconfig
```

![rosymenu](menu.png)
