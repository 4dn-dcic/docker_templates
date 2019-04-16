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
    libxml2-dev

# R 3.5
# r-base, r-base-dev for R 3.5, libcurl4-openssl-dev, libssl-dev for devtools
#RUN echo "deb https://cloud.r-project.org/bin/linux/ubuntu xenial-cran35/" >> /etc/apt/sources.list
RUN apt-get install -y apt-transport-https software-properties-common  # to add add-apt-repository and to avoid method driver could not be found error
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9 && \
    add-apt-repository 'deb [arch=amd64,i386] https://cran.rstudio.com/bin/linux/ubuntu xenial-cran35/' && \
    apt-get update -y && apt-get install -y \
    libcurl4-openssl-dev \
    libssl-dev \
    r-base \
    r-base-dev

RUN R -e 'install.packages("httr", repos="http://cran.us.r-project.org")'
RUN R -e 'install.packages("memoise", repos="http://cran.us.r-project.org")'
RUN R -e 'install.packages("whisker", repos="http://cran.us.r-project.org")'
RUN R -e 'install.packages("jsonlite", repos="http://cran.us.r-project.org")'
RUN R -e 'install.packages("git2r", repos="http://cran.us.r-project.org")'
RUN R -e 'install.packages("roxygen2", repos="http://cran.us.r-project.org")'
RUN R -e 'install.packages("https://cran.r-project.org/src/contrib/Archive/devtools/devtools_1.13.5.tar.gz", repos=NULL, type="source")'  # 2.0.2 doesn't work
RUN R -e 'install.packages("BiocManager", repos="http://cran.us.r-project.org")'


# default command
CMD ["bash"]

