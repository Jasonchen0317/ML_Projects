# Task 1: Drone Object Detection

This task is about detecting frames from the videos that includes the drone and finding the drone's bounding box.

## Approach

#### Part 1: Download videos and get frames

For downloading videos, first put the link of the videos in video_list. I used pytube library for downloading the videos, which will be saved in the 'video' folder. Next, I used cv2 to get the frames of the videos, and save the frames in 'dataset/test', 'dataset' directory includes training, validation, and testing dataset.
This part is all included in assignment-3.ipynb.

#### Part 2: Drone Object Detection

Training and Validation Dataset: https://www.kaggle.com/datasets/dasmehdixtr/drone-dataset-uav , I picked about 500 images for training, and about 100 images for validating.

The other python files are for drone detection: 

config.py includes the configurations such as dataset paths, hyperparameters for the model, classes, etc. 

custom_utils.py includes functions for saving trained models, saving plots, transforming images, etc. 

datasets.py is used is for converting raw datas to datasets that fits the input of the model. 

model.py builds the model for this task, which is the fasterrcnn_resnet50_fpn model from torchvision. 

train.py will be run to start training the model. The output includes best model and loss plots. 

detect.py will be run to detect the drones from the frames collected in part 1 using the trained model. The outputs is saved in detections directory.

## Training Loss Plot
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/assignment-3/readme_img/train_loss.png)

## Validation Loss Plot
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/assignment-3/readme_img/valid_loss.png)

## Some captured frames in video 1
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/assignment-3/readme_img/Video_0.gif)

## Some captured frames in video 2
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/assignment-3/readme_img/Video_1.gif)
