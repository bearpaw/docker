# Torch7 with CUDA8.0 cudnn5 Ubuntu16.04 with additional torch7 packages
# Wei Yang
# platero.yang@gmail.com
FROM nightseas/cuda-torch
MAINTAINER Wei Yang <platero.yang@gmail.com>

# Install dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
         build-essential \
         libhdf5-serial-dev \
         cmake \
         git \
         curl \
         vim \
         ca-certificates \
         libjpeg-dev \
         libpng-dev &&\
     rm -rf /var/lib/apt/lists/*

RUN luarocks install hdf5 && \
    luarocks install matio && \
    luarocks install optnet
