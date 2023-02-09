

# 📖 Report

## ⁉️ Specifications

**The need for interaction between humans and robots in different tasks and situations is becoming increasingly felt in the culinary field due to overpopulation and the many orders from citizens to eat at home.**

In order to respond to this need, the emergence of collaboration between humans and robots - hence the term "cobot" - has given rise to a field of research that has emerged to define and structure these collaborative interactions: HRI (Human-Robot Interaction). This field encompasses several areas of study: robotics (design of the robot's functioning), ergonomics (the study of the relationship between the human and the cobot, including the safety and user psychology), and design (the most aesthetically and economically viable model for the conceptualized robot).

The concept of Dark Kitchen - an English term adopted into common French usage to describe "virtual restaurants" or "ghost kitchens" that are only accessible online through food delivery platforms on the Internet - has become very widespread. However, the managers and entrepreneurs of these virtual restaurants face a major problem: recruitment difficulties, since this type of restaurant is generally located on the outskirts of cities and few people are motivated to work there due to the perceived bleak atmosphere and lack of social interaction. That's why cooking robots have been sought after by these companies at the KOBOTIK society.

<img src="https://github.com/Yoan-GitHub/Kobotik-Cuisine/blob/567edc01d4642c515fbd245a4d2545d2613339ef/assets/img/dark_kitchen.png">

The project therefore consists first and foremost in validating whether it is possible to link cobotics and gastronomy (standards, hygiene, etc.) and to conceptualize robotic processes to make a salad autonomously by the robot. 

**The study will therefore focus on developing an object recognition system (using Intel RealSense camera) serving two main objectives:**
> Teaching the cobot to recognize ingredients through reinforcement learning.
> Allowing the cobot to be able to alert the operator of the shortage of ingredients before reaching the lowest level.

To obtain the exact position of the center of the bowl that contains the ingredient we are interested in, we have the Intel RealSense camera (provided by our tutor) which gives us the coordinates of the point we want in real-time. We have decided that the best location for the camera within the robot mechanism would be in the center facing the ingredients.

To achieve this, we developed an ingredient recognition algorithm based on the **TensorFlow library for object detection**, which allows the robot to recognize the ingredients given by the user to prepare a salad completely _autonomously_.

### Is this work necessary?
The resolution approach we developed allows the robot to learn to recognize any ingredient provided by the user, based solely on a database of images of that food. **While several food recognition solutions are already available as open source on the web, these solutions are not trained on specific ingredients and are more generic. On the other hand, our solution is specific to our case and allows the cook robot to recognize any food, in stainless steel bins.**

## 🔎 Implemented approch

Our resolution approach first consists of creating a **database of ingredient images** which will then be used to test the **developed ingredient recognition algorithm** which is outlined in the [👨‍💻 Developer documentation](docs/developer).
The the diagram below summarizes our approach : 
<img src="https://github.com/Yoan-GitHub/Kobotik-Cuisine/blob/704aa8aea76aef0997a5e6bc237556549bd24d02/assets/img/UML_KOBOTIK_cuisine.png">

## 📈 Analysis of results

By executing the following command in Tensorflow/workspace/models/my_ssd_mobnet/eval :

    tensorboard --logdir=.

We obtain a http://localhost:6006/ link in the terminal which allows access to the model evaluation results.

> We then have the loss, precision, and recall function curves which are presented below :
**- Our loss function evolution for 5000 epochs:**
<img src="https://github.com/Yoan-GitHub/Kobotik-Cuisine/blob/12f2ad7fe01661eeaa5025e495b01d9d021f2a8b/assets/img/loss_5000epochs.png">

**- Our precision function evolution for 5000 epochs:**
<img src="https://github.com/Yoan-GitHub/Kobotik-Cuisine/blob/12f2ad7fe01661eeaa5025e495b01d9d021f2a8b/assets/img/precision.png">

**- Our recall function evolution for 5000 epochs:**
<img src ="https://github.com/Yoan-GitHub/Kobotik-Cuisine/blob/12f2ad7fe01661eeaa5025e495b01d9d021f2a8b/assets/img/recall.png">

Draw conclusions, **interpret** the results and make recommandations to your client for your future of the work.
It is totally fine to have results that are not as good as initially expected. Be honest and analyse why you did not manage to reach the objectives.
