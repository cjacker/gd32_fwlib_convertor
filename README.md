# gd32F/E/C/W/L Firmware Library convertor

A script to convert GD32F/E/C/L/W  official firmware library to gcc and makefile project

usage:

```
./gd32_fwlib_convertor <official firmware library rar or zip>
```

it's not good, there is still a lot of work need to do manually after converted, but works.

Tested with all firmware libraries from GigaDevice, 5 of them failed due to lack some CMSIS headers, after supply these missing header files, all firmware library built successfully.

```
GD32C10x_Firmware_Library_V1.1.1.rar
GD32C11x_Firmware_Library_V1.0.1.rar
GD32E10x_Firmware_Library_V1.3.1.rar
GD32E11x_Firmware_Library_V1.0.1.rar
GD32E23x_Firmware_Library_V1.1.5.rar : [FAILED] core_cm23.h missing
GD32E50x_Firmware_Library_v1.2.4.rar : [FAILED] cmsis_gcc.h missing
GD32F10x_Firmware_Library_V2.2.4.rar 
GD32F1x0_Firmware_Library_V3.4.0.rar : [FAILED] core_cmInstr.h missing
GD32F20x_Firmware_Library_V2.4.0.rar
GD32F30x_Firmware_Library_V2.1.5.rar
GD32F3x0_Firmware_Library_V2.2.0.rar
GD32F403_Firmware_Library_V2.1.5.rar
GD32F4xx_Firmware_Library_V3.0.3.rar
GD32L23x_Firmware_Library_V1.0.3.rar : [FAILED] core_cm23.h missing
GD32W51x_Firmware_Library_V1.0.2.zip : [FAILED] core_cm33.h missing
```

All missing file can be downloaded from : https://github.com/ARM-software/CMSIS_5/tree/develop/CMSIS/Core/Include. For example:

```
wget https://raw.githubusercontent.com/ARM-software/CMSIS_5/develop/CMSIS/Core/Include/core_cm33.h
```
Change the last filename 'core_cm33.h' to what you want.

**NOTE:** This script not works with gd32vf103 risc-v firmware library, it's already gcc ready.

Here is the [pre-converted gd32vf103 firmware library](https://github.com/cjacker/gd32vf103_firmware_library_gcc_makefile).
