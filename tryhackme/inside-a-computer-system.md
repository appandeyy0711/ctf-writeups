# Inside a Computer System

**Platform:** TryHackMe (Pre Security)
**Date:** 6 Nov 2026

## Main components
- **Motherboard:** The main board that connects components like CPU,GPU,RAM,SSD & PSU.It is just like a skeleton & nervous system.It has dedicated ports & slots for each components.
- **CPU:** It is the brain of computer system. It continuously executes instructions.
- **RAM:** It is temporary & fast memory.When working on a task,it holds data that the CPU needs quick access to. Data is lost when you power off your PC.
- **ROM:** the firmware chip on the motherboard that stores UEFI/BIOS.
- **Storage (SSD/HDD):** SSD/HDD are long term storage devices. Storage connects via SATA cables or PCI Express slots.It keeps data even when power off.
- **GPU:** The graphics card is comparable to the visual cortex of our brain.It receives information from the operating system and programs, then outputs processed visual data to a monitor.
- **PSU:** PSU supplies energy to all system components.PSU is essential and requires careful consideration - If components need more power than the PSU can provide,if it can't supply enough power,The System may Crash,restart,or fail to boot.



## What happens when I press the power button
1. PSU supplies power to motherboard.
2. UEFI(BIOS) firmware initializes and coordinates components. It is the first software that runs.
3. UEFI(firmware) runs POST to check that required hardware is present,configured,and functioning.
4. Firmware finds the boot device using the boot order.
5. Firmware loads the bootloader.
6. Bootloader loads the OS kernel.
7. OS starts drivers and services, then shows the login screen.

## BIOS vs UEFI vs OS
- **BIOS:** performs POST and hands off hardware control to the bootloader.
- **UEFI:** Initializes hardware, handles secure boot verification, and loads the OS boot manager. It can also perform POST.
- **OS:** Manages system hardware resources, drivers, CPU, memory, and provides the user interface/applications.
## What I learned
I was surprised to see what is going inside,when I press a PowerKey.
I learned about all the basic components of motherboard and how system boots up. I am sharing the boot sequence here,
THE BOOT SEQUENCE;
-Power -> UEFI -> POST -> Boot Device -> OS
-The bootloader loads the OS kernels RAM and hands over control to the OS.
-The operating system then starts loading the necessary files and services to bring the computer to life.


## Security link (my own thought)
Why would an attacker want to target the boot process?
