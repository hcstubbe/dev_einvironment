FROM pytorch/pytorch:2.5.0-cuda12.4-cudnn9-devel
                     
# Install dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    git \
    curl \
    wget \
    gnupg2 \
    && rm -rf /var/lib/apt/lists/*

# Download and install Ollama
RUN wget -qO - https://ollama.com/install.sh | bash

# Install Python packages
RUN pip install --upgrade pip && \
    pip install --upgrade --no-cache-dir "git+https://github.com/huggingface/transformers.git" && \
    pip install pandas sqlalchemy trl peft accelerate bitsandbytes ollama && \
    pip install "unsloth[cu124-ampere-torch250] @ git+https://github.com/unslothai/unsloth.git"
    # pip install "unsloth[cu121-torch240] @ git+https://github.com/unslothai/unsloth.git"
    

# Create a default user
RUN useradd -ms /bin/bash defaultuser
USER defaultuser

# Set the working directory
WORKDIR /home/defaultuser

ENV OLLAMA_MODELS=/home/defaultuser/.ollama/models

# Start the container with an endless running task
CMD [ "/bin/sh" , "-c", "tail -f /dev/null" ]