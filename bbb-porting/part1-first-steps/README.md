Click [here](00-factory.md) for testing the board with factory image,updating debian image in eMMC

# Packages to be collected

Prebuilt Toolchain, gcc-linaro-arm-linux-gnueabihf-4.9-2014.09_linux.tar.xz from https://releases.linaro.org/archive/14.09/components/toolchain/binaries/

Kernel source customized based on https://github.com/RobertCNelson/bb-kernel, KERNEL.tar.gz is hosted in this repository for initial use.

Configuration file hosted in this repository

Root file system image(bbb-rootfs.img hosted in this repository) prepared based on the rootfs template core-image-minimal-beaglebone.tar.bz2 from http://downloads.yoctoproject.org/releases/yocto/yocto-2.1/machines/beaglebone/

U-Boot source code (optional for initial work)

# Expected outcome

Kernel image -- uImage or zImage

Device tree blob(dtb) file -- am335x-boneblack.dtb

Rootfs/initrd image (optional) -- bbb-rootfs.img

# First steps towards booting the board

Click [here](01-simple.md) for simple building steps to prepare outcome

Click [here](02-expert.md) for some expert steps on building

Click [here](03-booting-methods.md) for some alternative booting methods





