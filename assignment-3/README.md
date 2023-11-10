# Task 1: Drone Object Detection

## Environment

Downloading videos: https://github.com/pytube/pytube

Training and Validation Dataset: https://www.kaggle.com/datasets/dasmehdixtr/drone-dataset-uav


## Approach

#### Part 1: Download videos and get frames

For downloading videos, first put the link of the videos in video_list. I used pytube library for downloading the videos, which will be saved in the 'video' folder. Next, I used cv2 to get the frames of the videos, and save the frames in 'dataset/test', 'dataset' directory includes training, validation, and testing dataset.
This part is all included in assignment-3.ipynb.

#### Part 2: Drone Object Detection

The other python files are for drone detection. 

config.py includes the configurations such as dataset path, hyperparameters for the model, classes, etc. 

custom_utils.py includes functions for saving trained models, save plots, transforming images, etc. 

datasets.py is used is for converting raw datas to dataset that will be fed to the model. 

model.py builds the model for this task, which is the fasterrcnn_resnet50_fpn from torch. 

train.py will be run to start training the model. The output includes best model and loss plots. 

detect.py will be run to detect the drones from the frames collected in part 1. The outputs is saved in detections directory.

## Training Loss Plot
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/assignment-3/readme_img/train_loss.png)

## Validation Loss Plot
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/assignment-3/readme_img/valid_loss.png)

## Some captured frames in video 1
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/assignment-3/readme_img/Video_0.gif)

## Some captured frames in video 2
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/assignment-3/readme_img/Video_1.gif)