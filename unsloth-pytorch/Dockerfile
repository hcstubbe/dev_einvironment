FROM pytorch/pytorch:2.4.0-cuda12.1-cudnn9-runtime

# Install dependencies
RUN apt-get update && apt-get install -y git python3-venv

# Create and activate virtual environment
RUN python3 -m venv /opt/venv
ENV PATH="/opt/venv/bin:$PATH"
ENV PYTHONPATH="/opt/venv/lib/python3.8/site-packages"

# Install PyTorch and other Python packages in the virtual environment
RUN pip install -U pip
RUN pip install -U sqlalchemy pandas transformers accelerate trl peft bitsandbytes
RUN pip install "unsloth[colab-new] @ git+https://github.com/unslothai/unsloth.git"

# Create a default user
RUN useradd -ms /bin/bash defaultuser
USER defaultuser

# Set the working directory
WORKDIR /home/defaultuser

# Start the container with an endless running task
CMD [ "/bin/sh" , "-c", "tail -f /dev/null" ]