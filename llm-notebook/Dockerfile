# Basis-Image von jupyter/tensorflow-notebook
FROM tensorflow/tensorflow:latest-gpu-jupyter

# Benutzer root für die Installation von Paketen
USER root

# Install dependencies
RUN apt-get update && apt-get install -y \
    wget \
    gnupg2 \
    && rm -rf /var/lib/apt/lists/*

# Download and install Ollama
RUN wget -qO - https://ollama.com/install.sh | bash

# Zurück zum Standardbenutzer
USER ${NB_UID}