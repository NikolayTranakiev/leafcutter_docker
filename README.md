# leafcutter_docker

This repository provides a container image with [leafcutter](https://github.com/davidaknowles/leafcutter) preinstalled for ease of use 


# Docker Setup Instructions

## Prerequisites
Download and install [Docker](https://docs.docker.com/get-docker/)

## Installation Steps

### 1. Pull image container from GitHub container registry:
```bash
docker pull ghcr.io/nikolaytranakiev/leafcutter-image:latest
```

### 2. Run Container:
```bash
docker run -it \
  -v /full/path/to/your/local/leafcutter_project:/workspace \
  -w /workspace \
  leafcutter-image:latest \
  /bin/bash
```

#### Parameter Explanation:
- `-it`: Combines two flags:
  - `-i` (interactive): Keeps STDIN open even if not attached
  - `-t` (tty): Allocates a pseudo-TTY for terminal interaction
- `-v /path/to/local:/workspace`: Volume mount that maps your local directory to `/workspace` inside the container
- `-w /workspace`: Sets the working directory inside the container to `/workspace`
- `leafcutter-image:latest`: The image name from GitHub Container Registry
- `/bin/bash`: The command to run inside the container (starts a bash shell)

### 3. Inside the Container:
Once the container is running, execute these commands:

```bash
# Activate the leafcutter conda environment
micromamba activate leafcutter

# Start R
R
```

