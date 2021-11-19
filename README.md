# Seq_nms_YOLO

#### Authors: Yunyun SUN, Yutong YAN, Sixiang XU, Heng ZHANG

---

## Introduction

![](img/index.jpg) 

This project combines **YOLOv2**([reference](https://arxiv.org/abs/1506.02640)) and **seq-nms**([reference](https://arxiv.org/abs/1602.08465)) to realise **real time video detection**.

## Set-up
1. Install requirements and activate virtual environment:
    * Install `venv` if needed: `pip -v install virtualenv`
    * Create a new Python 2 virtual environment: `virtualenv -p python2 yolo_env`
    * Activate this virtual environment: `source yolo_env/bin/activate`
    * Install requirements in this virtual environment: `pip install scipy==1.2.2 matplotlib tensorflow-gpu==1.15.0 opencv-python==4.2.0.32 Pillow tf-object-detection`
2. `make` the project. The Makefile is ready to use CUDA 10.1 to take advantage of the GPU.
3. Download `yolo.weights` running: `wget https://pjreddie.com/media/files/yolo.weights` 
4. You can download `tiny-yolo.weights` as well: `wget https://pjreddie.com/media/files/yolov2-tiny.weights`

## Execution
1. Copy a video file to the video folder, for example, `input.mp4`
2. In the video folder, run `python video2img.py -i input.mp4` and then `python get_pkllist.py`
3. Return to root floder and run `python yolo_seqnms.py` to generate output images in `video/output`
4. If you want to reconstruct a video from these output images, you can go to the video folder and run `python img2video.py -i output`

Detection results will be saved to in `video/output`.

## Reference

This project copies lots of code from [darknet](https://github.com/pjreddie/darknet) , [Seq-NMS](https://github.com/lrghust/Seq-NMS) and  [models](https://github.com/tensorflow/models).
