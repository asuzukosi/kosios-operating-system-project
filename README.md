This is the implementation of a minimal kernel, based on the barebones tutorial on OSDev https://wiki.osdev.org/Bare_Bones#Writing_a_kernel_in_C

This projects you have already built a cross compiler for the i686-elf target system

The commands used are:
To compile the assembly code:
    i686-elf-as boot.s -o boot.o

To compile the kernel c code:
    i686-elf-gcc -c kernel.c -o kernel.o -std=gnu99 -ffreestanding -O2 -Wall -Wextra

To link the code and produce the final operating system executable file
    i686-elf-gcc -T linker.ld -o kosios.bin -ffreestanding -O2 -nostdlib boot.o kernel.o -lgcc
To ensure that the boot command is valid:
    grub-file --is-x86-multiboot kosios.bin
