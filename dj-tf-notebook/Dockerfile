# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.
ARG OWNER=jupyter
ARG BASE_CONTAINER=$OWNER/tensorflow-notebook
FROM $BASE_CONTAINER

LABEL maintainer="Hans Christian Subbe <hstubbe@med.lmu.de>"

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

USER root


# Djanog and MariaDB/mysqlclient pre-requisites
RUN apt-get update --yes && \
    apt-get install --yes --no-install-recommends \
        python3-dev \
        default-libmysqlclient-dev \
        build-essential && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Install mysqlclient
RUN pip3 install --upgrade pip && \
    pip3 install --no-cache mysqlclient && \
    pip3 install --no-cache Django psycopg2-binary
# RUN conda install pomoxis

WORKDIR "${HOME}"
