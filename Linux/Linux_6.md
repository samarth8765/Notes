- Boot process
    - First stage - BIOS or UEFI(Unified Extensible Firmware Interface) runs some power on self test on different devices in our system to check if eveything is working fine or not.
    - Bootloader - BIOS or UEFI loads the bootloader which loads kernel into the memory.
    - Kernel initializes different devices in our system and init or mother process in our system.

- Three levels of abstraction in linux
    - Hardware, things like CPU, RAM, SSD's.
    - Kernel, managing our system
    - User-space

- Privilege level (protection rings)
    - Kernel -> Kernel mode
    - User -> user mode
