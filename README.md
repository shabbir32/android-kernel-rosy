# Clean 3.18 CAF kernel for Xiaomi Redmi 5

Completely clean and minimal kernel base. Use only with sane device trees, else you may experience issues for which I am not responsible at all.

##### Example of good trees:

Device tree: [1](https://github.com/NullDecoder/android_device_xiaomi_rosy.git) [2](https://github.com/baunilla/android_device_xiaomi_rosy.git)\
Vendor tree: [1](https://github.com/NullDecoder/android_vendor_xiaomi_rosy.git) [2](https://github.com/baunilla/android_vendor_xiaomi_rosy.git)\
Recovery tree: [1](https://github.com/NullDecoder/android_recovery_xiaomi_rosy.git)

Thanks to [@NullDecoder](https://github.com/NullDecoder) and [@baunilla](https://github.com/baunilla) for the trees!

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

##### Features:
```
* Clean and minimal imports of code for rosy.
* Can be compiled with GCC 8.3.0, all code warnings are fixed.
* Compiler optimizations.
* Latest prima (Wi-Fi) drivers from CAF.
* NTFS read-write support.
* F2FS support.
```

##### Information:
```
- CAF tag LA.UM.7.6.r1-05900-89xx.0 (Linux 3.18.120). Not upstreamed.
- CPU governors: [interactive], conservative, ondemand, userspace, powersave, performance.
- I/O schedulers: [cfq], noop, deadline.
- TCP algorithms: [westwood], cubic, reno.
- Compression algorithms: [lz4], lzo.
```

## Branches

##### p-3.18-base:
```
Information:

- CAF tag LA.UM.7.6.r1-05900-89xx.0
- For Android 9 (P).
```

##### q-3.18-base:
```
Information:

- SAR kernel.
- CAF tag LA.UM.7.6.r1-05900-89xx.0
- For Android 10 (Q).
```

## Cloning & building

This kernel contains submodules. To build it successfully, you have to either clone it with `--recursive` option or do `git submodule update --init --recursive` in the kernel directory after cloning.

Make sure you're building the kernel with `rosy_defconfig`.
