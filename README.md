## OliverS_FruitRipeness_Project


For my project, I decided to make a detection system that detects an image of apples, bananas, or oranges to see if they are ripe, unripe, or rotten. I chose this idea because it could help many different people in real life, such as farmers who harvest apples, bananas, or oranges, or shoppers who are looking for good fruit. It started with me going to Kaggle and downloading a dataset called "Fruit Ripeness: Unripe, Ripe, and Rotten". In this dataset, there many different images in the categories of each of the three fruits. After I downloaded the dataset, I trained my model for 35 epochs (this took about 2 hours). Then, I tested my model with 3 different images in each category and every single image was classified correct. The model's average confidence was about 97% with many of the fresh and rotten images being in the 99 to 100% range while the unripe images averaged between 70-95% on average. In the end, my model is a really good way for shoppers and farmers to find out whether or not an orange, apple, or banana is ripe, unripe, or rotten, but you can only use it for these fruits in their un-peeled/un-sliced form.




Example of Test: https://drive.google.com/file/d/1q5y-yjTi5U9hMzOvigLitfkGjL1k0t2R/view?usp=sharing 



# Kaggle Dataset
For my project, I downloaded a dataset called "Fruit Ripeness: Unripe, Ripe, and Rotten" by a user named Leftin on Kaggle. This dataset has 39,900 images of ripe, unripe, and rotten fruits. The three fruits in the dataset are apples, bananas, and oranges. I used these images to train my model to recognize whether the fruits were ripe or not.


This is the link for the dataset on Kaggle: https://www.kaggle.com/datasets/leftin/fruit-ripeness-unripe-ripe-and-rotten


Video explanation: https://drive.google.com/file/d/1gdK6kJDGGzuR7s0vXGrnq17S0xNt5RU_/view?usp=sharing




## The Algorithm
To train the model, I ran a command in the docker of Jetson-Inference to prompt the training. This was the command: python3 train.py --model-dir=models/dataset data/dataset. This made the model run through 35 different epochs of every single image in the folder which trained it to recognize whether fruits are unripe, ripe, or rotten. In my project, I used a neural network on Jetson-Inference called Image-net. Image-net lets you use the AI to scan images and uses image classification to determine what each object is. Also, for Image-net, what you have to do is train the model to recognize certain things that you want. For me, I did it to recognize whether fruits apple, banana, and orange are ripe, unripe, or rotten.

How to get clone Jetson-Inference from GitHub:

    git clone --recursive --depth=1 https://github.com/dusty-nv/jetson-inference


## Running this project


1. Steps for Running this Project.


# Steps
To use my model, you must:

1. Go to my GitHub post and download my model into VS Code


2. Enter your image of a banana, apple, or orange into jetson-inference/python/training/classification/data/dataset/test/TestHere


3. Name your image Test.png(Or jpg or any other image type)


4. In your terminal, run this command: 
    
        cd jetson-inference/python/training/classification

    
5. Run this command:
  
       NET=models/fruitmodel  DATASET=data/dataset


8. Run this command(make sure to replace test.png and the text in the ()s after with your image name):
  
        imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/TestHere/Test.png(or replace png with any other image type) TestPhoto.jpg


11. Click your image to see results


# Documentation
These are some examples of ripe, unripe, and rotten fruit images that I ran:

Apples:
        1. https://drive.google.com/file/d/1EusvHMNdR-uVSLOxlDeyTtyf1wWbf8O4/view?usp=sharing
        2. https://drive.google.com/file/d/1Yuvkl9sig12LaSleOUIamSYbAk1G2IGm/view?usp=sharing 
        3. https://drive.google.com/file/d/1QXi3UgW5qVqG05ZwQmp_niZfWGytk7YM/view?usp=sharing 

Bananas:
        1. https://drive.google.com/file/d/10a7QJUK2qrIDuL-s6UUDLKi-_335p4WN/view?usp=sharing 
        2. https://drive.google.com/file/d/1Eb6nEwZgJJ9i21yUZmuyckxAsc1k1rjB/view?usp=sharing 
        3. https://drive.google.com/file/d/1XC53tDchmyWE5WaSokep-Am9u7-VBIZI/view?usp=sharing 

Oranges:
        1. https://drive.google.com/file/d/1ohDhccwvPQ_tL37TPSRN9AjZOT7PSGCI/view?usp=sharing
        2. https://drive.google.com/file/d/13VCSR-bT25F1bHBLhsB2Gu8Re7yKPbDF/view?usp=sharing
        3. https://drive.google.com/file/d/1f4GyyBUJoK1hO2E8jm1bCAcpI9fyfaza/view?usp=sharing


This is the link to the planning document that I made before I started my project: https://docs.google.com/document/d/116cEfDgkRmzl7fPiYbzr0SGxpogb3c_0XX9uppdWtPE/edit?usp=sharing 
