# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.
ARG OWNER=jupyter
ARG BASE_CONTAINER=$OWNER/datascience-notebook
FROM $BASE_CONTAINER

LABEL maintainer="Hans Christian Subbe <hstubbe@med.lmu.de>"

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

USER root


# Pomoxis pre-requisites
RUN apt-get update --yes && \
    apt-get install --yes --no-install-recommends \
        zlib1g-dev \
        libncurses5-dev \
        libhdf5-dev \
        libatlas-base-dev \
        libopenblas-base \
        libopenblas-dev \
        libbz2-dev \
        liblzma-dev \
        libffi-dev \
        make \
        cmake \
        wget \
        bzip2 \
        curl \
        libcurl4-gnutls-dev && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

RUN apt-get update --yes && \
    apt-get install --yes --no-install-recommends \
        miniasm samtools bcftools && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

WORKDIR /etc
RUN git clone https://github.com/lh3/minimap2 && \
    cd minimap2 && make
ENV PATH="/etc/minimap2:${PATH}"

WORKDIR /etc
RUN git clone --recursive https://github.com/lbcb-sci/racon.git racon  && \
    cd racon  && \
    mkdir build  && \
    cd build  && \
    cmake -DCMAKE_BUILD_TYPE=Release ..  && \
    make
ENV PATH="/etc/racon/build/bin:${PATH}"


RUN pip install --upgrade biopython

RUN conda config --add channels defaults && \
    conda config --add channels bioconda && \
    conda config --add channels conda-forge

# RUN conda install pomoxis
RUN conda install -y -c bioconda seqkit

RUN pip install --no-cache-dir git+https://github.com/rrwick/Porechop

RUN pip install --no-cache-dir nbdev 

# RUN conda install pomoxis

WORKDIR "${HOME}"




