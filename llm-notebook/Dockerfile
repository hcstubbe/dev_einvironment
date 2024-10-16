# Basis-Image von jupyter/tensorflow-notebook
FROM jupyter/tensorflow-notebook

# Benutzer root für die Installation von Paketen
USER root

# Install dependencies
RUN apt-get update && apt-get install -y \
    wget \
    gnupg2 \
    && rm -rf /var/lib/apt/lists/*

# Install NVIDIA driver, CUDA toolkit, and cuDNN
RUN apt-get update && apt-get install -y \
    nvidia-driver-460 \
    cuda-toolkit-11-2 \
    libcudnn8=8.1.1.33-1+cuda11.2 \
    libcudnn8-dev=8.1.1.33-1+cuda11.2 \
    && rm -rf /var/lib/apt/lists/*

# Download and install Ollama
RUN wget -qO - https://ollama.com/install.sh | bash

# Zurück zum Standardbenutzer
USER ${NB_UID}