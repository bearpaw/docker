# Pytorch 1.0.1, CUDA 10, CUDNN 7
# Wei Yang
# platero.yang@gmail.com
FROM nvidia/cuda:10.0-cudnn7-devel-ubuntu16.04
ARG PYTHON_VERSION=3.7
RUN apt-get update && apt-get install -y --no-install-recommends \
         build-essential \
         cmake \
         git \
         curl \
         vim \
         ca-certificates \
         libjpeg-dev \
         libpng-dev &&\
     rm -rf /var/lib/apt/lists/*


RUN curl -o ~/miniconda.sh -O  https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh  && \
     chmod +x ~/miniconda.sh && \
     ~/miniconda.sh -b -p /opt/conda && \
     rm ~/miniconda.sh && \
     /opt/conda/bin/conda install -y python=$PYTHON_VERSION numpy pyyaml scipy ipython mkl mkl-include cython typing && \
     /opt/conda/bin/conda install -y -c pytorch magma-cuda100 && \
     /opt/conda/bin/conda clean -ya
ENV PATH /opt/conda/bin:$PATH
RUN pip install ninja

# install PyTorch
RUN conda install -y -c pytorch \
    cudatoolkit=10.0 \
    torchvision=0.2.1 \
    "pytorch=1.0.1=py3.7_cuda10.0.130_cudnn7.4.2_2" \
&&  conda clean -ya

# Install any needed packages specified in requirements.txt
RUN pip install numpy>=1.8.4
RUN pip install matplotlib>=1.4.2
RUN pip install EasyDict>=1.7
RUN pip install opencv-python>=3.4.1.15
RUN pip install Cython
RUN pip install scipy
RUN pip install pandas
RUN pip install pyyaml
RUN pip install json_tricks
RUN pip install scikit-image
RUN pip install tensorboardX>=1.2
RUN pip install tqdm>=4.19.8
RUN pip install spacepy==0.1.6
RUN pip install requests>=2.19.1

# Set the working directory to /app
WORKDIR /app
