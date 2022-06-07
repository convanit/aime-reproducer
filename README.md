# aime-reproducer

original notebook from https://github.com/tensorflow/docs/blob/master/site/en/tutorials/images/transfer_learning.ipynb and converted to .py script
(https://www.tensorflow.org/tutorials/images/transfer_learning)


code to reproduce CUDA_ERROR_LAUNCH_FAILED with tensorflow and cuda, cudnn using nvidia containers (e.g https://docs.nvidia.com/deeplearning/frameworks/tensorflow-release-notes/rel_21-05.html#rel_21-05)

Host System is: Ubuntu Linux 20.04.4, Kernel: Linux 5.13.0-44-generic on x86_64
NVIDIA Container Toolkit: 2.7.0-1

## RUN

1. cd in to this repo and 

2. run the container
```docker run --gpus all -it --rm -v ${PWD}:/workspace nvcr.io/nvidia/tensorflow:21.05-tf2-py3```

3. inside the container run:
```pip install matplotlib && python transfer.py```

The training stops randomly at some training epoch with messages like this:


```
59/63 [===========================>..] - ETA: 0s - loss: 0.2117 - accuracy: 0.91262022-06-07 14:39:27.774512: E tensorflow/stream_executor/cuda/cuda_event.cc:29] Error polling for event status: failed to query event: CUDA_ERROR_LAUNCH_FAILED: unspecified launch failure
2022-06-07 14:39:27.774576: F tensorflow/core/common_runtime/gpu/gpu_event_mgr.cc:220] Unexpected Event status: 1
Aborted (core dumped)
```

## Installed Host packages from nvidia

libnvidia-cfg1-515 515.48.07-0ubuntu1		NVIDIA binary OpenGL/GLX configuration library

libnvidia-common-515 515.48.07-0ubuntu1		Shared files used by the NVIDIA libraries

libnvidia-compute-418 430.50-0ubuntu3		Transitional package for libnvidia-compute-430

libnvidia-compute-430 515.48.07-0ubuntu1		Transitional package for libnvidia-compute-515

libnvidia-compute-515 515.48.07-0ubuntu1		NVIDIA libcompute package

libnvidia-compute-515 515.48.07-0ubuntu1		i386 NVIDIA libcompute package

libnvidia-container-tools 1.9.0-1		NVIDIA container runtime library (command-line tools)

libnvidia-container1 1.9.0-1		NVIDIA container runtime library

libnvidia-decode-515 515.48.07-0ubuntu1		NVIDIA Video Decoding runtime libraries

libnvidia-decode-515 515.48.07-0ubuntu1		i386 NVIDIA Video Decoding runtime libraries

libnvidia-encode-515 515.48.07-0ubuntu1		NVENC Video Encoding runtime library

libnvidia-encode-515 515.48.07-0ubuntu1		i386 NVENC Video Encoding runtime library

libnvidia-extra-515 515.48.07-0ubuntu1		Extra libraries for the NVIDIA driver

libnvidia-fbc1-515 515.48.07-0ubuntu1		NVIDIA OpenGL-based Framebuffer Capture runtime library

libnvidia-fbc1-515 515.48.07-0ubuntu1		i386 NVIDIA OpenGL-based Framebuffer Capture runtime library

libnvidia-gl-515 515.48.07-0ubuntu1		NVIDIA OpenGL/GLX/EGL/GLES GLVND libraries and Vulkan ICD

libnvidia-gl-515 515.48.07-0ubuntu1		i386 NVIDIA OpenGL/GLX/EGL/GLES GLVND libraries and Vulkan ICD

nvidia-compute-utils-515 515.48.07-0ubuntu1		NVIDIA compute utilities

nvidia-container-toolkit 1.9.0-1		NVIDIA container runtime hook

nvidia-dkms-515 515.48.07-0ubuntu1		NVIDIA DKMS package

nvidia-docker2 2.10.0-1		nvidia-docker CLI wrapper

nvidia-driver-515 515.48.07-0ubuntu1		NVIDIA driver metapackage

nvidia-kernel-common-515 515.48.07-0ubuntu1		Shared files used with the kernel module

nvidia-kernel-source-515 515.48.07-0ubuntu1		NVIDIA kernel source package

nvidia-prime 0.8.16~0.20.04.2		Tools to enable NVIDIA's Prime

nvidia-settings 515.48.07-0ubuntu1		Tool for configuring the NVIDIA graphics driver

nvidia-utils-515 515.48.07-0ubuntu1		NVIDIA driver support binaries

nvtop 1.0.0-1ubuntu2		Interactive NVIDIA GPU process monitor

screen-resolution-extra 0.18build1  	Extension for the nvidia-settings control panel

xserver-xorg-video-nvidia-515 515.48.07-0ubuntu1