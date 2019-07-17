FROM ubuntu:16.04
MAINTAINER Soo Lee (duplexa@gmail.com)

# 1. general updates & installing necessary Linux components
RUN apt-get update -y && apt-get install -y \
    bzip2 \
    curl \
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
    libssl-dev \
    software-properties-common \
    apt-transport-https

# installing conda
RUN wget https://repo.continuum.io/miniconda/Miniconda3-4.5.4-Linux-x86_64.sh && bash Miniconda3-4.5.4-Linux-x86_64.sh -p /miniconda3 -b
ENV PATH=/miniconda3/bin:$PATH
RUN conda update -y conda \
    && rm Miniconda3-4.5.4-Linux-x86_64.sh
RUN conda config --add channels bioconda

# docker inside docker
RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add - \
    && add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
RUN apt-get update -y \
    && apt-cache policy docker-ce \
    && apt-get install -y docker-ce

# supporting UTF-8
ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8

# default command
CMD ["bash"]

