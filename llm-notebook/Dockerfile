# Basis-Image von jupyter/tensorflow-notebook
FROM quay.io/jupyter/pytorch-notebook:cuda12-latest

# Benutzer root für die Installation von Paketen
USER root

# Install dependencies
RUN apt-get update && apt-get install -y \
    wget \
    gnupg2 \
    && rm -rf /var/lib/apt/lists/*

# Download and install Ollama
RUN wget -qO - https://ollama.com/install.sh | bash

# Install PyTorch
RUN pip install -U sqlalchemy pandas ollama transformers accelerate
RUN pip install -U git+https://github.com/huggingface/trl.git
RUN pip install --upgrade pip && pip install "unsloth[cu121-torch240] @ git+https://github.com/unslothai/unsloth.git"

# Default user
USER ${NB_UID}