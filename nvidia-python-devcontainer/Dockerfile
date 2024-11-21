FROM nvidia/cuda:12.1.0-runtime-ubuntu22.04

# Avoid prompts during installation
ENV DEBIAN_FRONTEND=noninteractive

# Install system dependencies
RUN apt-get update && apt-get install -y \
    python3.10 \
    python3-pip \
    git \
    && rm -rf /var/lib/apt/lists/*

# Set up Python environment
ENV PATH="${PATH}:/home/vscode/.local/bin"
RUN python3 -m pip install --upgrade pip

# Install Python libraries
RUN pip install \
    jupyterlab \
    transformers \
    datasets \
    evaluate \
    accelerate \
    torch \
    bitsandbytes \
    peft \
    wandb \
    tqdm \
    scipy \
    numpy \
    "pybind11<2.0" \
    scikit-learn \
    ipywidgets==8.1.5 \
    jupyter==1.1.1 \
    widgetsnbextension \
    jupyterlab-widgets

# Clean up
RUN apt-get clean && rm -rf /var/lib/apt/lists/*