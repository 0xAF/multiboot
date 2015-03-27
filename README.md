# 0xAF MultiBoot USB #
----------------------
0xAF MultiBoot USB, set of instructions and configuration files to create a MultiBoot USB Drive.

***

## Install ##
Information comes from [pendrivelinux.com](http://www.pendrivelinux.com/boot-multiple-iso-from-usb-via-grub2-using-linux/)

1. `export USBDRIVE=/dev/sdX`
2. prepare one fat32 (type: c) partition on $USBDRIVE, set it bootable
3. `mkfs.vfat -F 32 -n MULTIBOOT ${USBDRIVE}1`
4. `mkdir /mnt/USB && mount ${USBDRIVE}1 /mnt/USB`
5. `grub2-install --force --no-floppy --boot-directory=/mnt/USB/boot $USBDRIVE`
6. copy and overwrite all files on USB drive with this repository

***

## Test ##
I'm testing the USB drive with QEMU:
`qemu-system-x86_64 -enable-kvm -smp 4 -m 256 -hda /dev/sdc`.
Use min 1024MB RAM to test Hiren's Boot CD (`-m 1024`)

***

## Some ideas ##
* <http://www.antionline.com/showthread.php?272072-Diagnostic-Utilities>
* <http://thanki.tk/>
* <http://www.ultrabootcd.com/listofutilities.htm>
* <http://www.resoo.org/docs/dos/free_software/system.htm>
* <http://ubcd.sourceforge.net/>

