FROM 4dndcic/ubuntu16.04-miniconda-python36:v1
MAINTAINER Soo Lee (duplexa@gmail.com)

#1 more updates & git update
RUN apt update -y && apt upgrade -y && \
    apt-get install -y python-software-properties software-properties-common && \
    add-apt-repository ppa:git-core/ppa -y && \
    apt-get update -y && \
    apt-get install git -y

#2 updating conda
RUN conda update -y conda

#3 installing mamba
RUN conda install -n base -c conda-forge mamba

#4 installing Cython
RUN pip install Cython

# supporting UTF-8
ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8

# default command
CMD ["bash"]

