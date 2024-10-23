FROM pytorch/pytorch:2.4.0-cuda12.1-cudnn9-runtime

# Set up environment variables
ENV LANG=C.UTF-8
ENV LC_ALL=C.UTF-8

# Install dependencies
RUN apt-get update && \
    apt-get install -y --no-install-recommends git
    
# Create a working directory
WORKDIR /workspace

# Install Python packages
RUN pip install --upgrade pip
RUN pip install --upgrade --no-cache-dir "git+https://github.com/huggingface/transformers.git"
RUN pip install pandas sqlalchemy trl peft accelerate bitsandbytes
RUN pip install "unsloth[cu121-torch240] @ git+https://github.com/unslothai/unsloth.git"

# Set the default command to bash
CMD ["bash"]
