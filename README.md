# FreeRTOS Ported to Raspberry Pi 2B

This provides a very basic port of FreeRTOS to Raspberry pi 2B, now with video!

## Howto Build

Type make

Currently the makefile expect an arm-none-eabi- toolchain in the path. Either export the path to yours or
modify the TOOLCHAIN variable in dbuild.config.mk file.

You may also need to modify the library locations in the Makefile:

    kernel.elf: LDFLAGS += -L"/usr/lib/gcc/arm-none-eabi/4.9.3" -lgcc
    kernel.elf: LDFLAGS += -L"/usr/lib/arm-none-eabi/lib" -lc

Format your SD card as FAT32
Copy the bootcode.bin and start.elf from here https://github.com/raspberrypi/firmware/tree/master/boot
Copy the config.txt from /boot_stuff onto the SD card to fix over/underscanning
Copy the kernel7.img generated by make

You should see the green LED turn on while the videotest happens, then the led will continuously blink.
