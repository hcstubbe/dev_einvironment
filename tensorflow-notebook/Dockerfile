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
        bedtools && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

WORKDIR "${HOME}"




