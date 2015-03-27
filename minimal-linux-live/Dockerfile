FROM        ubuntu:trusty
MAINTAINER  Cooper Maa <coopermaa77@gmail.com>
            
ENV         IMG_VERSION 07-Feb-2015

# Install dependencies for minimal linux live and qemu, git...
# see http://minimal.linux-bg.org/
RUN         DEBIAN_FRONTEND=noninteractive && apt-get update && apt-get install -y \
            wget build-essential bc syslinux genisoimage \
            libncurses5-dev git tree qemu
            
RUN         git clone https://github.com/ivandavidov/minimal/ && \
            cd minimal && \
            git checkout $IMG_VERSION
              
ADD         ./run /minimal/src/
ADD         ./fix-dns /minimal/src/

WORKDIR     /minimal/src

RUN         ./build_minimal_linux_live.sh

# How to use this image:
#  Here we add "NET_ADMIN" capability to allow qemu to configure the network
#  without this you won't able connect to outside world
# $ docker run -it --cap-add=NET_ADMIN coopermaa/minima-linux-live