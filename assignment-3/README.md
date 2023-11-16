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

detect.py will be run to detect the drones from the frames collected in part 1 using the trained model. The outputs will be saved in the 'detections' directory. Only a part of the detected frames are uploaded due to the limitation of github. The frames are converted back to videos and saved in 'detections_video' folder.

## Training Loss Plot
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/assignment-3/readme_img/train_loss.png)

## Validation Loss Plot
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/assignment-3/readme_img/valid_loss.png)

## Some captured frames in video 1
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/assignment-3/readme_img/Video_0.gif)

## Some captured frames in video 2
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/assignment-3/readme_img/Video_1.gif)


# Task 2: Kalman Filter 

This task aim to implement a Kalman filter that will track the drone in the video.

## Approach

Most part of task 2 is based on detect.py from task 1, since the output of the detection model will be used as the measurement for the kalman filter. 

#### Kalman filter instance variable

1. Filter state estimate(x) is composed by coordinates of the center of the bounding box (cx,cy), size of the box (width, height) and the change of each of these parameters, velocities.

2. Covariance matrix(P) is set to I*10 (np.eye(8) * 10.).

3. Process uncertainty/noise(Q) is set to I*0.01 (np.eye(8) * 0.01).

4. Measurement uncertainty/noise(R) is set 1 for center point, 10 for width and height.

#### Steps

First, the bounding box is found by the Faster-RCNN model, then is converted into the format of the measurement for the filter. The filter first predicts and then uses the measurement to update the resulting bounding box. 
For small amount(<20) of consecutive frames that has no detection, I've used the kalman filter to predict the bounding boxes, since it maybe false negative(miss detection). If the amount of consecutive frames that has no detection is over the threshold, the saved detected frames will be output as videos. 