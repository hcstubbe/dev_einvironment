FROM pytorch/pytorch:2.4.0-cuda12.1-cudnn9-runtime

# Install dependencies
RUN apt-get update && apt-get install -y \
    git \
    wget \
    curl \
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