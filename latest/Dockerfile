FROM ubuntu:22.04

LABEL maintainer="m4j0rt0m <major.tom.spaceworm@gmail.com>"

# install prerequisite software
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y \
    build-essential clang bison flex \
    libreadline-dev gawk tcl-dev libffi-dev git \
    graphviz xdot pkg-config python3 libboost-system-dev \
    libboost-python-dev libboost-filesystem-dev zlib1g-dev && \
    apt-get clean

ENV DOCK=/opt/docker
RUN mkdir $DOCK
WORKDIR $DOCK

# install yosys
RUN cd $DOCK && \
    git clone https://github.com/YosysHQ/yosys.git yosys --recurse-submodules && \
    cd yosys && \
    make -j$(nproc) && \
    make install

# remove downloaded stuff
RUN cd $DOCK && \
    rm -rf ./*

# force the use of bash
RUN ln -sf /bin/bash /bin/sh

WORKDIR /root
