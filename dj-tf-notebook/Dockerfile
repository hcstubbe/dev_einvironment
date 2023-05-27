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
    pip3 install --no-cache Django psycopg2-binary django-pwa django-environ whitenoise
# RUN conda install pomoxis

WORKDIR "${HOME}"

RUN mkdir '/home/lcarsm'

RUN chown -R jovyan:users "${HOME}"
RUN chown -R jovyan:users '/home/lcarsm'


USER jovyan
