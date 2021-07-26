#!/usr/bin/docker
# Title:            libguestfs-dev
# Author:           Sick.Codes https://github.com/sickcodes
# Version:          1.45.6
# License:          GPLv2
# Repository:       https://github.com/sickcodes/libguestfs-dev
# Website:          https://sick.codes
# 
#   docker build -t libguestfs-dev .
#   docker run  libguestfs-dev
#   docker run --name libguestfs-dev libguestfs-dev
#   docker cp . libguestfs-dev:/home/arch/aur/libguestfs-dev/

FROM archlinux:base-devel

MAINTAINER 'https://github.com/sickcodes' <https://sick.codes>

SHELL ["/bin/bash", "-c"]

RUN useradd arch \
    && echo 'arch ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers \
    && mkdir -p /home/arch

RUN pacman -Syyu git --noconfirm

USER arch

ENV USER=arch

RUN sudo chown -R arch:arch /home/arch

WORKDIR /home/arch

RUN git clone https://github.com/sickcodes/aur.git

WORKDIR /home/arch/aur

RUN mkdir -p /home/arch/aur/libguestfs-dev

COPY . /home/arch/aur/libguestfs-dev

WORKDIR /home/arch/aur/libguestfs-dev

ENV LIBGUESTFS_DEBUG=1
ENV LIBGUESTFS_TRACE=1

CMD /bin/bash -c "makepkg -si --syncdeps --noconfirm"
