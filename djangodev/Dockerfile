# Select base image
ARG BASE_IMG_VER=3.12-alpine

# Create build image
FROM python:${BASE_IMG_VER} as base
RUN apk add --update --virtual .build-deps \
    build-base \
    postgresql-dev \
    python3-dev \
    libpq \
    musl-dev \ 
    mariadb-dev

# Use virtualenv
RUN python -m venv --copies /opt/venv
ENV PATH="/opt/venv/bin:$PATH"

# Install python packages
COPY requirements.txt requirements.txt
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# Second build stage
FROM python:${BASE_IMG_VER}
RUN apk add --update \
    mariadb-connector-c \
    bash \
    git
COPY --from=base /opt/venv /opt/venv

# Use virtualenv
ENV PATH="/opt/venv/bin:$PATH"

# Run as non-root
RUN addgroup -S lcarsm && adduser -S lcarsm -G lcarsm
USER lcarsm