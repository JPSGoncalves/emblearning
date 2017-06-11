# Simple Steps to prepare the expected outcome

Choose a suitable directory, say eworkdir under your home directory, we'll refer it as ~/eworkdir from now onwards

## Prepare the pre built toolchain

### For 32 bit systems:-

Extract gcc-linaro-6.2.1-2016.11-i686_arm-linux-gnueabihf.tar.xz in ~/eworkdir

tar -xvf gcc-linaro-6.2.1-2016.11-i686_arm-linux-gnueabihf.tar.xz

You may rename to short convenient name

mv gcc-linaro-6.2.1-2016.11-x86_64_arm-linux-gnueabihf gcc-linaro-6.2.1

### For 64 bit systems:-

 extract gcc-linaro-6.2.1-2016.11-x86_64_arm-linux-gnueabihf.tar.xz instead of gcc-linaro-6.2.1-2016.11-i686_arm-linux-gnueabihf.tar.xz
 and rename to gcc-linaro-6.2.1

### Common:-
Update PATH with new binaries in ~/eworkdir/gcc-linaro-6.2.1/bin as follows

export PATH=$HOME/eworkdir/gcc-linaro-6.2.1/bin:$PATH

The above setting is temporary and applicable to current shell only, add this to ~/.bashrc or ~/.bash_profile to take
this setting effective for every launch of new shell(~/.bashrc) or every login(~/.bash_profile

After slight experience you can place the toolchain in /opt instead of ~/eworkdir, in such case /opt/gcc-linraro-6.2.1 to be add to PATH variable,you may ignore this step initially!!

export PATH=/opt/gcc-linaro-6.2.1/bin:$PATH

and update to .bashrc or .bash_profile as usual.

## Building the kernel

Extract the given tar ball with kernel source in workdir, i.e. ~/eworkdir

tar -zxvf KERNEL.tar.gz -C ~/eworkdir

Let's call the extracted kernel source, i.e. ~/eworkdir/KERNEL as KSRC from now onwards

Follow these steps for custom building of kernel source for the target

make ARCH=arm mrproper

#copy config-4.9.0-step1 as .config in KSRC

make ARCH=arm menuconfig   #for further changes may skip initially

make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- zImage modules dtbs

Locate arch/arm/boot/zImage,arch/arm/boot/dts/am335x-boneblack.dtb w.r.t KSRC and copy them to a temporary directory say ~/eworkdir/deploy


## Preparing rootfs

## Your First Boot
