FROM ubuntu:16.04
MAINTAINER Soo Lee (duplexa@gmail.com)

# 1. general updates & installing necessary Linux components
RUN apt-get update -y && apt-get install -y \
    bzip2 \
    gcc \
    git \
    less \
    libncurses-dev \
    make \
    time \
    unzip \
    vim \
    wget \
    zlib1g-dev \
    liblz4-tool

# installing python3.5 & pip
RUN apt-get update -y && apt-get install -y \
    python3.5-dev \
    python3-setuptools \
    && wget https://bootstrap.pypa.io/get-pip.py \
    && python3.5 get-pip.py

# supporting UTF-8
ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8

# default command
CMD [ "bash" ]

