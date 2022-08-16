# GestureRecognition
Develop a feature for the smart-TV that can recognise five different gestures performed by the user which will help users control the TV without using a remote.

The training data consists of a few hundred videos categorised into one of the five classes. Each video (typically 2-3 seconds long) is divided into a sequence of 30 frames(images). These videos have been recorded by various people performing one of the five gestures in front of a webcam - similar to what the smart TV will use. 

The gestures are continuously monitored by the webcam mounted on the TV. Each gesture corresponds to a specific command:

Thumbs up:  Increase the volume
Thumbs down: Decrease the volume
Left swipe: 'Jump' backwards 10 seconds
Right swipe: 'Jump' forward 10 seconds  
Stop: Pause the movie

You can find the data set here : https://drive.google.com/drive/folders/1JHlKrrYVGg9A22sGg_1MvbprcNo63e9L?usp=sharing

The data is in a zip file. The zip file contains a 'train' and a 'val' folder with two CSV files for the two folders. 
These folders are in turn divided into subfolders where each subfolder represents a video of a particular gesture. Each subfolder, i.e. a video, contains 30 frames (or images). Note that all images in a particular video subfolder have the same dimensions but different videos may have different dimensions. Specifically, videos have two types of dimensions - either 360x360 or 120x160 (depending on the webcam used to record the videos). Hence, we will need to do some pre-processing to standardise the videos. 

Each row of the CSV file represents one video and contains three main pieces of information - the name of the subfolder containing the 30 images of the video, the name of the gesture and the numeric label (between 0-4) of the video.

Our objective task is to train a model on the 'train' folder which performs well on the 'val' folder as well (as usually done in ML projects).

For analysing videos using neural networks, two types of architectures are used commonly. One is the standard CNN + RNN architecture in which you pass the images of a video through a CNN which extracts a feature vector for each image, and then pass the sequence of these feature vectors through an RNN. 

The other popular architecture used to process videos is a natural extension of CNNs - a 3D convolutional network. Where is the only change is to use 3-D convolutions instead of 2-D.

We used :
CNN - To extract useful features from the frames of images of each video.
RNN - To extract semantic information of the sequence of those feaures.
