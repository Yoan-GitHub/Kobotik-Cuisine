# 📖 Developer documentation

## Purpose of this documentation

Welcome to the documentation for the "KOBOTIK Cuisine" project. This guide is designed specifically for future developers who will be reusing and building upon the work done here. As a fellow developer with the same skill set, we understand the importance of clear and comprehensive documentation. Our aim with this guide is to provide you with a thorough understanding of the code structure and how it can be easily extended to add new features. Whether you are a student taking over from where we left off, or simply interested in using this project as a starting point for your own work, we hope that this documentation will be a valuable resource for you.

## Do we really need to feed this section? 

Maybe not, if your project does not include code or if it is trivial. If so, drop the section and the links.


## What is expected here

This project was proposed to us as part of our Robotics and AI option within our ENSEIRB-Matmeca engineering school. The goal is to train ourselves in new technologies while building on the knowledge already acquired in robotics and AI development. To successfully continue this project, the following foundations are required: good knowledge of the Python language and the functioning of a supervised learning neural network. A computer, camera, and ingredients must also be available.


If you have the preceding prerequisites, you are ready to start the project. The following documentation is divided into two major parts:

A hands-on approach to the KOBOTIK Cuisine robot.
A thorough understanding of the developed AI model.

# Part 1:  HANDS-ON APPROACH TO THE ROBOT 

### Step 1.  Connect to the cobot  

Kook up with the cobot. Choose the program to run. Enter the cobot ip address : <img width="306" alt="image" src="https://user-images.githubusercontent.com/81220020/217781328-fddea825-b347-4ced-8362-eaa83f347ab0.png">

### Step 2. Install dependencies  

     git clone git@github.com:xArm-Developer/xArm-Python-SDK.git
     cd xArm-Python-SDK
     python setup.py install

### Step 3. To obtain images with the program rotation_cobot :

If you use a realsense camera, start the video acquisition at the same time as the program. Once the program is finished, a .bag file is created. To convert it to a folder containing the images, go to this link https://github.com/IntelRealSense/librealsense/releases/tag/v2.50.0 then downloading and running the installer file Intel.RealSense.SDK-WIN10. Open Command Prompt window,go to the Tools folder which the rs-convert is located.

     cd C://Program Files (x86)/Intel RealSense SDK 2.0/Tools

Input the rs-convert conversion command : 

     rs-convert.exe -i "YOUR_BAG_FILE_DIR\example.bag" -v "DIR_FOR_THE_CONVERTED_FILE"

### Step 3 bis. To take ingredients with the program mouvement_robot :

Install the gripper on the cobot and put a spoon between the claws. Have two bins and a bowl like this : 

     ![image](https://user-images.githubusercontent.com/81220020/217786917-76775964-df82-48db-b92a-cacf8b029d15.png)

Change the id to 1 if you want the cobot go to the first bin and change the id to 2 if you want the cobot go to second bin.

<img width="242" alt="image" src="https://user-images.githubusercontent.com/81220020/217786192-951a1f76-8512-49db-9cbc-fb468ee4fcdd.png">

Then run the program.

###

# Part 2: DEVELOPED AI MODEL

### Step 1. Clone this repository: https://github.com/Yoan-GitHub/Kobotik-Cuisine

### Step 2.  Create a new virtual environment 

    python -m venv tfod

### Step 3. Activate your virtual environment 

    source tfod/bin/activate # Linux
    .\tfod\Scripts\activate # Windows 


 ### Step 4. Install dependencies and add virtual environment to the Python Kernel 
 
    python -m pip install --upgrade pip
    pip install ipykernel
    python -m ipykernel install --user --name=tfod

### Step 5. Collect images 
> Collect images using the Notebook 1. Image Collection.ipynb - ensure you change the kernel to the virtual environment as shown below:
<img src = "https://github.com/Yoan-GitHub/Kobotik-Cuisine/blob/398cc644f5f4b9daebb2405e452fd8b1e6eba7b8/assets/img/step5.png">


### Step 6.  Create Train et Test folders
> Manually divide collected images into two folders train and test. So now all folders and annotations should be split between the following two folders.
    \TFODCourse\Tensorflow\workspace\images\train
    \TFODCourse\Tensorflow\workspace\images\test 


### Step 7. 
> Begin training process by opening 2. Training and Detection.ipynb, this notebook will walk you through installing Tensorflow Object Detection, making detections, saving and exporting your model. 


### Step 8. Install Tensorflow Object Detection
> During this process the Notebook will install Tensorflow Object Detection. You should ideally receive a notification indicating that the API has installed successfully at Step 8 with the last line stating OK.
<img src = "https://github.com/Yoan-GitHub/Kobotik-Cuisine/blob/cd755a6e66f666d9b8f008723c51ab7df681ec70/assets/img/step8.png">


### Step 9. Train the model
> Once you get to step 6. Train the model, inside of the notebook, you may choose to train the model from within the notebook. We noticed however that training inside of a separate terminal on a Windows machine you're able to display live loss metrics. 
<img src = "https://github.com/Yoan-GitHub/Kobotik-Cuisine/blob/cd755a6e66f666d9b8f008723c51ab7df681ec70/assets/img/step9.png">


### Step 10. Evaluate the model
> You can optionally evaluate your model inside of Tensorboard. Once the model has been trained and you have run the evaluation command under Step 7. Navigate to the evaluation folder for your trained model e.g. 

    cd Tensorlfow/workspace/models/my_ssd_mobnet/eval
 
and open Tensorboard with the following command 
    tensorboard --logdir=. 
 
Tensorboard will be accessible through your browser and you will be able to see metrics including mAP - mean Average Precision, and Recall. (screen)







