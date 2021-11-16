# Seq_nms_YOLO

#### Membres: Yunyun SUN, Yutong YAN, Sixiang XU, Heng ZHANG

---

## Introduction

![](img/index.jpg) 

This project combines **YOLOv2**([reference](https://arxiv.org/abs/1506.02640)) and **seq-nms**([reference](https://arxiv.org/abs/1602.08465)) to realise **real time video detection**.

## Steps
1. Install requirements and activate virtual environment 
`pip -v install virtualenv
virtualenv -p python2 yolo_env
source yolo_env/bin/activate
pip install scipy==1.2.2 matplotlib tensorflow-gpu==1.15.0 opencv-python==4.2.0.32 Pillow tf-object-detection`;
3. `make` the project;
4. Download `yolo.weights` and `tiny-yolo.weights` by running: `wget https://pjreddie.com/media/files/yolo.weights` and `wget https://pjreddie.com/media/files/yolov3-tiny.weights`;
5. Copy a video file to the video folder, for example, `input.mp4`;
6. In the video folder, run `python video2img.py -i input.mp4` and then `python get_pkllist.py`;
7. Return to root floder and run `python yolo_seqnms.py` to generate output images in `video/output`;
8. If you want to reconstruct a video from these output images, you can go to the video folder and run `python img2video.py -i output`

And you will see detection results in `video/output`

## Reference

This project copies lots of code from [darknet](https://github.com/pjreddie/darknet) , [Seq-NMS](https://github.com/lrghust/Seq-NMS) and  [models](https://github.com/tensorflow/models).
