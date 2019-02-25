# Dockerfile

This repository maintains the Dockerfiles I used.

# Build Docker image
```
docker build --tag=pytorch:1.0.1-py3.7-cuda10.0-cudnn7 \
pytorch/1.0.1-py3.7-cuda10.0-cudnn7-runtime-ubuntu16.04
```

Test example:
```
docker run --rm -it --init \
  --runtime=nvidia \
  --ipc=host \
  --user="$(id -u):$(id -g)" \
  --volume=$PWD:/app \
  pytorch:1.0.1-py3.7-cuda10.0-cudnn7 \
  python /app/hello-pytorch.py
```
results should be like:
```
Hello, Docker world!
Python ver: 3.7.2 (default, Dec 29 2018, 06:19:36)
[GCC 7.3.0]
PyTorch ver: 1.0.1.post2
```
