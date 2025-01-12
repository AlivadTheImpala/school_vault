RAM: ram is a volatile memory, meaning that the memory that is stored there is only temporary and serves the purpose of reading data from an open applicaiton quickly, but the data is wiped when the computer is shut off.

ROM: similar to ROM in that its faster than a harddrive, but instead of being volatile it is non-volatile so even a power shutoff wont clear its memory. It'll typically hold the BIOS which is the first software that runs when a system boots and helps start the other computer processes. 

Kernel Mode: kernel mode is the closest to the core components to a computer. It allows full access to system resources and hardware so higher privilege levels are required. Applications running in kernel mode are all tied to a single address space.

User Mode: when you launch a program in user mode it has its own virtual address space, each program is private and therefore other programs cant modify another's data. 

I/O Manager: running in kernal mode the I/O manager acts as a bridge between user mode programs and the hardware that governs input and output interactions. 

Device Driver: 