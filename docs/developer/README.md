# 📖 Developer documentation

## ⁉️ Purpose of this documentation

Welcome to the documentation for the "KOBOTIK Cuisine" project. This guide is designed specifically for future developers who will be reusing and building upon the work done here. As a fellow developer with the same skill set, we understand the importance of clear and comprehensive documentation. Our aim with this guide is to provide you with a thorough understanding of the code structure and how it can be easily extended to add new features. Whether you are a student taking over from where we left off, or simply interested in using this project as a starting point for your own work, we hope that this documentation will be a valuable resource for you.

## ⁉️ Do we really need to feed this section? 

Maybe not, if your project does not include code or if it is trivial. If so, drop the section and the links.


## ⁉️ What is expected here

This project was proposed to us as part of our Robotics and AI option within our ENSEIRB-Matmeca engineering school. The goal is to train ourselves in new technologies while building on the knowledge already acquired in robotics and AI development. To successfully continue this project, the following foundations are required: good knowledge of the Python language and the functioning of a supervised learning neural network. A computer, camera, and ingredients must also be available.


If you have the preceding prerequisites, you are ready to start the project. The following documentation is divided into two major parts:

A hands-on approach to the KOBOTIK Cuisine robot.
A thorough understanding of the developed AI model.

# Part 1: * HANDS-ON APPROACH TO THE ROBOT * 

# Part 2: DEVELOPED AI MODEL

## Step 1. Clone this repository: lien github

## Step 2. 
> Create a new virtual environment 

python -m venv tfod

## Step 3. 
> Activate your virtual environment 

    source tfod/bin/activate # Linux
    .\tfod\Scripts\activate # Windows 


 ## Step 4. 
 > Install dependencies and add virtual environment to the Python Kernel 
 
    python -m pip install --upgrade pip
    pip install ipykernel
    python -m ipykernel install --user --name=tfod

## Step 5. 
> Collect images using the Notebook 1. Image Collection.ipynb - ensure you change the kernel to the virtual environment as shown below ( screen )



## Step 6. 
> Manually divide collected images into two folders train and test. So now all folders and annotations should be split between the following two folders.
    \TFODCourse\Tensorflow\workspace\images\train
    \TFODCourse\Tensorflow\workspace\images\test 


## Step 7. 
> Begin training process by opening 2. Training and Detection.ipynb, this notebook will walk you through installing Tensorflow Object Detection, making detections, saving and exporting your model. 


## Step 8. 
> During this process the Notebook will install Tensorflow Object Detection. You should ideally receive a notification indicating that the API has installed successfully at Step 8 with the last line stating OK. (screen)


## Step 9. 
> Once you get to step 6. Train the model, inside of the notebook, you may choose to train the model from within the notebook. We noticed however that training inside of a separate terminal on a Windows machine you're able to display live loss metrics. (screen)


## Step 10. 
> You can optionally evaluate your model inside of Tensorboard. Once the model has been trained and you have run the evaluation command under Step 7. Navigate to the evaluation folder for your trained model e.g. 

    cd Tensorlfow/workspace/models/my_ssd_mobnet/eval
 
and open Tensorboard with the following command 
    tensorboard --logdir=. 
 
Tensorboard will be accessible through your browser and you will be able to see metrics including mAP - mean Average Precision, and Recall. (screen)







