## General
This repo contains a dockerfile and src files for orriaga's [face-classification](https://github.com/oarriaga/face_classification) routines

Installs Python3, Tensorflow-gpu, OpenCV3.1 and supporting libraries

## Build
Prereqs: openhorizon/cogwerx-x86_64-cudabase container image (CUDA libs in ubuntu xenial)
Build time on native x86_64 Core i7: ~15 min 
Image size: raw: 15GB, using `docker --squash`: 7GB

`docker build --force-rm -f Dockerfile.dev -t openhorizon/cogwerx-x86_64-face-classification-opencv3.1:v0.1 .`

## Pull container
Container image: https://hub.docker.com/r/openhorizon/cogwerx-x86_64-face-classification-opencv3.1/

`docker pull openhorizon/cogwerx-x86_64-face-classification-opencv3.1:v0.1`

## Run
`xhost + && docker run -it --rm -e DISPLAY=$DISPLAY -v /tmp:/tmp --privileged openhorizon/cogwerx-x86_64-face-classification-opencv3.1:v0.1 /bin/bash`
`cd face_classification/src`
`python3 video_emotion_color_demo.py`
