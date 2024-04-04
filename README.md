# thingy53-qspi
Hacked together thingy that lets you write to and read from the external flash chip on a Thingy:53.

Can technically be integrated into a project but should not be considered a proper driver.

**ONLY WORKS FOR SECURE APPLICATIONS!**

Change the `QSPI_BASE` and `GPIO_BASE` macros in `src/qspi.s` if you wish to build for a non-secure application.

## What's in this repo

`src/qspi.s` contains the actual asm code interacting with the peripheral.

`src/qspi.c` provides C wrappers for the aforementioned asm code.

`src/main.c` is a simple test function to make the project buildable, it reads the first 4 bytes of flash and prints out the read value.

## How to build

```sh
west build -p -b thingy53_nrf5340_cpuapp
west flash
```
