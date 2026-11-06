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
## Security Link (My Own Thoughts)

### Why Would an Attacker Want to Target the Boot Process?

The boot process is an attractive target for attackers because it executes before the operating system becomes fully operational.

- **It runs early:** Boot components execute before many OS-level security tools, such as antivirus and EDR solutions, are fully loaded. This can give boot-level malware an opportunity to interfere with security mechanisms.

- **It operates with high privileges:** Firmware and boot components operate at highly privileged execution levels. Compromising them may allow an attacker to tamper with the operating system before it starts.

- **It can survive OS reinstallation:** Firmware-level malware may remain even after the operating system is wiped and reinstalled because it resides in motherboard firmware rather than ordinary disk storage.

  Real-world examples include **LoJax**, the first UEFI rootkit discovered in the wild, and **BlackLotus**, a UEFI bootkit that exploited a vulnerability to bypass Secure Boot protections on vulnerable systems.

- **It is difficult to detect:** Many traditional security tools focus on monitoring the running operating system and may have limited visibility into firmware-level threats.

**Key takeaway:** Securing the boot process is important because compromising it can undermine the security of the operating system before the OS even starts.
