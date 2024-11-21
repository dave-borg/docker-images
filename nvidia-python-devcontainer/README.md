# README
## Overview
This repository contains a Dockerfile that sets up a development environment for Python with NVIDIA CUDA support. The Docker image is based on nvidia/cuda:12.1.0-runtime-ubuntu22.04 and includes various Python libraries and tools commonly used for machine learning and data science.

## Dockerfile Details
The Dockerfile performs the following steps:

1. Base Image: Uses the nvidia/cuda:12.1.0-runtime-ubuntu22.04 image as the base image.
2. Environment Variables: Sets DEBIAN_FRONTEND=noninteractive to avoid prompts during installation.
3. System Dependencies: Installs system dependencies including Python 3.10, pip, and git.
4. Python Environment: Adds the local bin directory to the PATH and upgrades pip.
5. Python Libraries: Installs a list of Python libraries including:
- jupyterlab
- transformers
- datasets
- evaluate
- accelerate
- torch
- bitsandbytes
- peft
- wandb
- tqdm
- scipy
- numpy
- pybind11<2.0
- scikit-learn
- ipywidgets==8.1.5
- jupyter==1.1.1
- widgetsnbextension
- jupyterlab-widgets
6. Clean Up: Cleans up the apt cache to reduce the image size.

## Usage
To build the Docker image, navigate to the directory containing the Dockerfile and run:

```bash
docker build -t nvidia-python-devcontainer .
```

To run a container from the built image, use:

```bash
docker run --gpus all -it nvidia-python-devcontainer
```

This will start a container with the specified environment, ready for Python development with CUDA support.

## Push the image

To push the Docker image to Docker Hub, follow these steps:

1. Tag the Image: Tag the image with your Docker Hub username and repository name.
2. Log In: Log in to Docker Hub.
3. Push the Image: Push the tagged image to Docker Hub.

Here are the commands:

```bash
# Tag the image
docker tag nvidia-python-devcontainer your_dockerhub_username/nvidia-python-devcontainer:latest

# Log in to Docker Hub
docker login

# Push the image
docker push your_dockerhub_username/nvidia-python-devcontainer:latest
```