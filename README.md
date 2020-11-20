# Seq_nms_YOLO

#### Membres: Yunyun SUN, Yutong YAN, Sixiang XU, Heng ZHANG

---

## Introduction

![](img/index.jpg) 

This project combines **YOLOv2**([reference](https://arxiv.org/abs/1506.02640)) and **seq-nms**([reference](https://arxiv.org/abs/1602.08465)) to realise **real time video detection**. The following code runs in a macbook pro with anaconda environment and python 3.7 version.

## Steps
ENVIRONMENT CREATION
1. Create the environment typing in a mac terminal from the project folder: `conda create -y --prefix ./env python=3.7 `;
1. Activate the environment with `source activate ./env`;

DEPENDENCIES NEEDED
2. `conda install -y -c conda-forge opencv`;
2. `conda install -y -c anaconda cudatoolkit=10.1`;
2. `conda install -y cudnn=7.6.4`;
2. `conda install -y numpy`;
2. `conda install -y -c menpo imageio `;

RUNNING THE CODE
1. `make` the project;
1. Download `yolo.weights` and `tiny-yolo.weights` by running `wget https://pjreddie.com/media/files/yolo.weights` and `wget https://pjreddie.com/media/files/yolov2-tiny-voc.weights`;
1. Copy a video file to the video folder, for example, `input.mp4`;
1. In the video folder, run `python video2img.py -i input.mp4` and then `python get_pkllist.py`;
1. Return to root floder and run `python yolo_seqnms.py` to generate output images in `video/output`;
1. If you want to reconstruct a video from these output images, you can go to the video folder and run `python img2video.py -i output`

And you will see detection results in `video/output`

## Reference

This project copies lots of code from [darknet](https://github.com/pjreddie/darknet) , [Seq-NMS](https://github.com/lrghust/Seq-NMS) and  [models](https://github.com/tensorflow/models).

