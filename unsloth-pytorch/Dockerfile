FROM pytorch/pytorch:2.4.0-cuda12.1-cudnn9-devel

# Install dependencies
RUN apt-get update && apt-get install -y git build-essential

# Install Python packages
RUN pip install --upgrade pip && \
    pip install --upgrade --no-cache-dir "git+https://github.com/huggingface/transformers.git" && \
    pip install pandas sqlalchemy trl peft accelerate bitsandbytes && \
    pip install "unsloth[cu121-torch240] @ git+https://github.com/unslothai/unsloth.git"

# Create a default user
RUN useradd -ms /bin/bash defaultuser
USER defaultuser

# Set the working directory
WORKDIR /home/defaultuser

# Start the container with an endless running task
CMD [ "/bin/sh" , "-c", "tail -f /dev/null" ]