# SBC6120 PDP-8 Single Board Computer

The Spare Time Gizmos SBC6120 is a more or less conventional single board computer with the typical complement of EPROM, RAM, a RS232 serial port, and an IDE disk interface.  What makes it unique is that the CPU is the Harris HD-6120 PDP-8 on a chip. The 6120 is the second generation of single chip PDP-8 compatible microprocessors and was used in Digital's DECmate-I, II, III and III+ "personal" computers.

The SBC6120 can run all standard DEC paper tape software, such as FOCAL-69, with no changes. Simply use the ROM firmware on the SBC6120 to download FOCAL69.BIN from a PC connected to the console port (or use a real ASR-33 and read the real FOCAL-69 paper tape, if you’re so inclined!), start at 200(8), and you’re running.  OS/278, OS/78 and, yes - OS/8 V3D or V3S - can all be booted on the SBC6120 using either RAM disk or IDE disk as mass storage devices. Since the console interface in the SBC6120 is KL8E compatible and does not use a HD-6121, there is no particular need to use OS/278 and real OS/8 V3D runs perfectly well.


## Hardware

* A completely PDP-8/E compatible instruction set.

* Built in KM8E compatible memory management.

* A separate 32KW control panel memory for a bootstrap/monitor.

* 64K twelve bit words of RAM - 32KW for panel memory and 32KW for conventional memory.

* 32KW of EPROM which contains the BTS6120 firmware.

* An optional RAM disk card containing up to 2Mb of eight bit of battery backed up, non-volatile SRAM.

*  A memory management system that controls the mapping of RAM, EPROM and RAM disk into the panel memory space.
bullet	

* A real, straight-8 compatible console terminal interface. The logic for this interface is implemented in a GAL - no 6121 is used and no software emulation is required.

* An IDE/ATA disk interface.

* A four LED display used to show POST error codes.


## Firmware

* A power on self test (POST) of the SBC6120 hardware, including the CPU, a memory test for EPROM, RAM and RAM disk, and a test of all peripheral devices.

* Commands to examine and change main memory or panel memory, plus commands to clear memory, move memory blocks, compute checksums, perform word searches, etc.

* Commands to examine and modify all 6120 registers.

* The ability to set break points in main memory programs, and to execute single instructions and generate instruction traces.

* A BIN format loader for loading paper tape images through the console port.

* RAM disk I/O functions to assist the OS/8 VM01 handler.

* IDE disk I/O functions to assist the OS/8 ID01 handler.

* Commands to upload and download both RAM and IDE disk over the serial port.

* An OS/8 bootstrap for both RAM and IDE disk.

* Support for the FP6120 front panel.


## Front Panel

The FP6120 adds a traditional PDP-8/E style Programmer’s Console (aka a lights and switches front panel) to any SBC6120 system. Twenty seven LEDS provide continuous display of the current memory address as well as memory or register contents, and a additional LED displays the running or halted state of the processor. Twelve data switches allow for direct entry of binary data and an additional eight switches provide program control functions including BOOT, ADDRESS LOAD, EXTENDED ADDRESS LOAD, CLEAR, CONTINUE, EXAMINE, DEPOSIT and HALT.

