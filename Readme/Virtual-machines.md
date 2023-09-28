<div id="top"></div>

<!-- Shields/Logos -->
[![License][license-shield]][license-url]
[![Issues][issues-shield]][issues-url]
[![Discord][discord-shield]][discord-url]
  
# Running LinuxLoops images in Virtual Machines

LinuxLoops disk images can be run in Virtual Machines by treating them as raw disks.  
**WARNING: Do not launch the currently running LinuxLoops image in a Virtual Machine. I don't see why anyone would want to do that but it will most likely break the image.**  

## QEMU

The boot mode needs to be set to EFI and disk images can natively be used as raw disks.  

## VirtualBox

1. From the OS with VirtualBox installed, cd into the linuxloops image folder.  

2. (Linux only) Make sure your user has ownership over the image file:  

`sudo chown myusername:myusername ubuntu.img`  

3. Create a virtual disk template for the linuxloops image:  

From Windows: `C:\"Program Files"\Oracle\VirtualBox\VboxManage.exe internalcommands createrawvmdk -filename ubuntu.vmdk -rawdisk ubuntu.img`  

From Linux: `vboxmanage internalcommands createrawvmdk -filename ubuntu.vmdk -rawdisk ubuntu.img`  

4. Open VirtualBox and setup a new virtual machine. When requested for the storage, select the vmdk file we have just created in the linuxloops image folder.  

5. Open the VM settings -> System -> enable EFI  

6. Start the VM  

<!-- Reference Links -->
<!-- Badges -->
[license-shield]: https://img.shields.io/github/license/sebanc/linuxloops?label=License&logo=Github&style=flat-square
[license-url]: ./LICENSE
[issues-shield]: https://img.shields.io/github/issues/sebanc/linuxloops?label=Issues&logo=Github&style=flat-square
[issues-url]: https://github.com/sebanc/linuxloops/issues
[discord-shield]: https://img.shields.io/badge/Discord-Join-7289da?style=flat-square&logo=discord&logoColor=%23FFFFFF
[discord-url]: https://discord.gg/x2EgK2M
