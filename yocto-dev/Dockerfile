FROM seawolf89/ubuntu-base

USER root
# install yocto tools
RUN DEBIAN_FRONTEND="noninteractive" apt-get install \
    --no-install-recommends -y \
    gawk wget git-core diffstat unzip texinfo gcc-multilib \
    build-essential chrpath socat cpio python3 python3-pip python3-pexpect \
    xz-utils debianutils iputils-ping python3-git python3-jinja2 \
    libegl1-mesa libsdl1.2-dev pylint3 iproute2 file iptables zstd liblz4-tool

RUN pip install kas

USER $USER
