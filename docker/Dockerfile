# Use the official Python image from the Docker Hub
FROM python:3.12-slim

# Install the required packages
RUN apt-get update && apt-get install -y \
    wget \
    curl \
    unzip \
    git \
    vim \
    nano \
    less \
    procps \
    && rm -rf /var/lib/apt/lists/*

# Set the working directory in the container
WORKDIR /opt

# Install the Tapestri Suite
RUN wget https://dl.missionbio.io/mosaic/mosaic-v3.7.0-Linux-x86_64.sh
RUN chmod +x mosaic-v3.7.0-Linux-x86_64.sh
RUN ./mosaic-v3.7.0-Linux-x86_64.sh -b -p /opt/mosaic

# Command to run the application
CMD ["bash"]