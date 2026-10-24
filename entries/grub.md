# Grub layers

## Kernel and HAL (hardware abstraction layer)
This is the layer that takes ready to be used, it includes achitecture-dependent code and generic-logic.  
grub-core/kern/ (Generic microkernel logic)  
grub-core/kern/\<platform\>/ (EFI, i386-pc, emu, coreboot)  
grub-core/osdep/ (Host OS hooks for utilities/emu)  
grub-core/fs/ and grub-core/disk/ (Base I/O drivers)  

## Presentation
This is the layer that present UI which includes reading the configuration files, render the UI (video or text)  
and wait for the user input.  
grub-core/normal/ (The framework that ties the UI together)  
grub-core/menu/ (Menu data structures and timeout logic)  
grub-core/script/ (The parser for grub.cfg)  
grub-core/video/ and grub-core/term/ (The abstract visual and text interfaces)  

## Loader
This layer is executed after a menu entry is selected, basically is the logit to load the kernel, initrd and anything  
needed described in the selected menu entry.  
grub-core/loader/ (General loader definitions)  
grub-core/loader/\<platform\>/ (e.g., efi/linux.c, i386/pc/chainloader.c, emu/linux.c)  
