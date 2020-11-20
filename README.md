# Seq_nms_YOLO

#### Membres: Yunyun SUN, Yutong YAN, Sixiang XU, Heng ZHANG

---

## Introduction

![](img/index.jpg) 

This project combines **YOLOv2**([reference](https://arxiv.org/abs/1506.02640)) and **seq-nms**([reference](https://arxiv.org/abs/1602.08465)) to realise **real time video detection**. The following code runs in a macbook pro with anaconda environment and python 3.7 version.

## Steps
ENVIRONMENT CREATION
1. Create the environment typing in a mac terminal from the project folder: `conda create -y --prefix ./env python=3.7 `
1. Activate the environment with `source activate ./env`

DEPENDENCIES NEEDED
1. `conda install -y -c conda-forge opencv`
1. `conda install -y -c anaconda cudatoolkit=10.1`
1. `conda install -y cudnn=7.6.4`
1. `conda install -y numpy`
1. `conda install -y -c menpo imageio`
1. `conda install -y matplotlib`
1. `conda install -y -c anaconda scipy`
1. `conda install -y -c conda-forge tensorflow`
1. `pip install tensorflow-object-detection-api`

RUNNING THE CODE
1. Include in the Makefile the lib/pkgconfig folder from your environment in the PKG_CONFIG_PATH by setting `PKG_CONFIG_PATH=$PKG_CONFIG_PATH:./env/lib/pkgconfig` and then `export PKG_CONFIG_PATH`
1. GPU acceleration is performed in Makefile for the specific parallel GPU's of the macbook pro, if working with a system with Nvidia GPU enable in the Makefile enable `CUDNN=1` and `GPU=1` and change change cuda-8.0 to cuda-10.1
1. `make` the project
1. Download `yolo.weights` and `tiny-yolo.weights` by running `wget https://pjreddie.com/media/files/yolo.weights` and `wget https://pjreddie.com/media/files/yolov2-tiny-voc.weights`
1. Copy libdarknet.so and libdarknet.a to env/lib by running from the main directory `cp libdarknet.so env/lib/` and `cp libdarknet.a env/lib/`
1. Copy a video file to the video folder, for example, `input.mp4`
1. In the terminal go to the video folder
1. In the video folder, run `python video2img.py -i input.mp4` and then `python get_pkllist.py`
1. Return to root folder and run `python yolo_seqnms.py` to generate output images in `video/output`
1. If you want to reconstruct a video from these output images, you can go to the video folder and run `python img2video.py -i output`

And you will see detection results in `video/output` named as output.mp4

## Reference

This project copies lots of code from [darknet](https://github.com/pjreddie/darknet) , [Seq-NMS](https://github.com/lrghust/Seq-NMS) and  [models](https://github.com/tensorflow/models).

