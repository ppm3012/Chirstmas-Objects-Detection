# Chirstmas-Objects-Detection

![image](https://user-images.githubusercontent.com/87477460/162230899-68edd6f0-63ff-45bb-a8ac-4435ec3fb054.png)

## Overview
In this notebook, I used YOLOv5 to detect the christmas related objects (Present, X_max tree and Person) on custom dataset.

## Insert repo and Custom Dataset
```bash
%%capture
!git clone https://github.com/ultralytics/yolov5.git
!curl -L "https://app.roboflow.com/ds/Shz7Lx2frG?key=YWkj112nrf" > roboflow.zip; unzip -o roboflow.zip; rm roboflow.zip
!pip install -r requirements.txt
!pip install wandb
%cd /content/yolov5
```
Before anything, I cloned <a>https://github.com/ultralytics/yolov5.git</a> and installed requirements.txt, weight and bias for detection process analysis.

## Create Custom Dataset
Since YOLOv5 models must be trained on labelled data in order to learn classes of objects in that data, I used Roboflow to label, prepare, and host my custom data automatically in YOLO format.

## Image Collection
My collected data are mostly from google image and some from Unsplash.

## Training
```bash
!python train.py \
  --data ../data.yaml \
  --epochs 80 \
  --project yolo-wandb-demo \
  --upload_dataset \
  --bbox_interval 1 \
  --save-period 1
  ```
  Then I trained the model with epoch 80.
  
  ![image](https://user-images.githubusercontent.com/87477460/162229327-5d8c0f94-19ae-4459-8c1b-470ea35213fa.png)

## Testing

![image](https://user-images.githubusercontent.com/87477460/162224552-41c929a2-5637-49f3-8d0a-c734c113de9e.png)

Finally, I picked a random image to see how correctly my model can predict.


