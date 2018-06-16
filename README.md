### Udacity-Self-Driving-Car-Nano-Degree-Behavioral-Cloning-Project
---

**Behavioral Cloning Project**

The goals / steps of this project are the following:
* Use the simulator to collect data of good driving behavior
* Build, a convolution neural network in Keras that predicts steering angles from images
* Train and validate the model with a training and validation set
* Test that the model successfully drives around track one without leaving the road
* Summarize the results with a written report

## Rubric Points
### Here I will consider the [rubric points](https://review.udacity.com/#!/rubrics/432/view) individually and describe how I addressed each point in my implementation.  

### Files Submitted & Code Quality

#### 1. Submission includes all required files and can be used to run the simulator in autonomous mode

My project includes the following files:
* Cloning.ipynb containing the script to create and train the model
* drive.py for driving the car in autonomous mode
* model.h5 containing a trained convolution neural network 
* README.md summarizing the results
* video.mp4 contains the driver view of the car self-driving around the path

### Model Architecture and Training Strategy

#### 1. An appropriate model architecture has been employed

I used the Nvidia network architecture to finish this project. The architecture of Nvidia network is shown as below. ![](/examples/cnn_nvidia.png).

#### 2. Attempts to reduce overfitting in the model

Add dropout layers in order to reduce overfitting (.7) after advises.

The model was trained and validated on different data sets (80% for training, 20% for validation, in model.fit(...validation_split = 0.2...)) to ensure that the model was not overfitting. The model was tested by running it through the simulator and ensuring that the vehicle could stay on the track.

#### 3. Model parameter tuning

The model used an adam optimizer, so the learning rate was not tuned manually.

#### 4. Appropriate training data

Training data was chosen to keep the vehicle driving on the road. In this project, I use three cameras. I train the car with the simulator for one lap. After this lap I found the car still drive off the road

The training dataset contains 8174 images and validation dataset contains 2044 images. 

Epochs was set 15 in the first time however, overfitting happened after 10 epochs so I change it to 7. And the patch size equals to 128 as usual

For details about how I created the training data, see the next section. 

### Model Architecture and Training Strategy

#### 1. Solution Design Approach

The overall strategy for deriving a model architecture was to ...

My first step was to use a convolution neural network model similar to the ... I thought this model might be appropriate because ...

In order to gauge how well the model was working, I split my image and steering angle data into a training and validation set. I found that my first model had a low mean squared error on the training set but a high mean squared error on the validation set. This implied that the model was overfitting. 

I think the more data I put in the system, the batter result I can get expecially on the big turns, if I only have 3000 images to train the model, the car always stuck on the corner or hit the bridge and stop moving.
