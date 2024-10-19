# Basis-Image von pytorch/pytorch
FROM quay.io/jupyter/pytorch-notebook:latest

# Benutzer root für die Installation von Paketen
USER root

# Install dependencies
RUN apt-get update && apt-get install -y \
    wget \
    gnupg2 \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Download and install Ollama
RUN wget -qO - https://ollama.com/install.sh | bash

# Add python packages
RUN pip install numpy pandas matplotlib scikit-learn sqlalchemy ollama

# Set standard user
USER ${NB_UID}