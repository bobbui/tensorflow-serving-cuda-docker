# tensorflow-serving-cuda-docker
Docker image for tensorflow serving with CUDA which suitable for development purpose

This image is based from nvidia/cuda:8.0-cudnn5-devel-ubuntu14.04 include: 
- ubuntu 14.04
- CUDA 8 with development packages
- cuDNN 5 with development packages
- bazel 0.4.4
- tensorflow 1.0.0
- tensorflow serving source code that is ready to build 
- other setting: proxy,enviroment variable, etc .

You can using either following dockerfile:
- Dockerfile: no tensorflow serving  build happen:  
- Dockerfile.GUI extended from above Dockerfile with GUI and VNC server:  
    connect to: vnc://<host>:5901 via VNC client. The VNC password is **password**. 
After build the docker image, run tensorflow serving compilication with the desired setting.

```
cd /serving/tensorflow
./configure
cd /serving
bazel build -c opt --config=cuda tensorflow_serving/...
bazel test tensorflow_serving/...
```
