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
    liblz4-tool \
    libcurl4-openssl-dev \
    libssl-dev 

# installing conda
RUN wget https://repo.continuum.io/miniconda/Miniconda3-4.5.12-Linux-x86_64.sh && bash Miniconda3-4.5.12-Linux-x86_64.sh -p /miniconda3 -b
ENV PATH=/miniconda3/bin:$PATH
RUN conda update -y conda \
    && rm Miniconda3-4.5.12-Linux-x86_64.sh
RUN conda config --add channels bioconda

# supporting UTF-8
ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8

# default command
CMD ["bash"]

