# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.
ARG OWNER=hstubbe
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

WORKDIR /etc
RUN git clone --recursive https://github.com/nanoporetech/pomoxis && \
	cd pomoxis && \
	make install && \
	. ./venv/bin/activate

WORKDIR "${HOME}"




