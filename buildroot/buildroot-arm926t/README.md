# buildroot-arm926t

Buildroot is an embedded Linux build system, builds from source for:

  * cross-compile toolchain
  * root filesystem with many libraries/applications, cross built
  * Linux Kernel and bootloader images

![buildroot](../buildroot.png)

This is dockerized buildroot with following features:

  * Based on [ubuntu:trusty](https://registry.hub.docker.com/_/ubuntu/) image
  * With buildroot installed, and pre-built toolchain for arm926t target
  * Additiona packages: git, qemu

## How to use buildroot-arm926t

Create a buildroot-arm926t container:

    $ docker run -it coopermaa/buildroot-arm926t

Then, start to use buildroot inside the container:

    # make [menu|x|n|g]config
    ...
    # make
    ...
    # ls output/images
    rootfs.tar     rootfs.ext2     zImage

Run the image with qemu:

    # cd output
    # qemu-system-arm -M versatilepb -kernel zImage -hda rootfs.ext2 \
      -append "root=/dev/sda console=ttyAMA0" -nographic