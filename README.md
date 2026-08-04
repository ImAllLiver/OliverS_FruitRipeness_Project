## OliverS_FruitRipeness_Project


For my project, I decided to make a detection system that detects an image of apples, bananas, or oranges to see if they are ripe, unripe, or rotten. I chose this idea because it could help many different people in real life, such as farmers who harvest apples, bananas, or oranges, or shoppers who are looking for good fruit. It started with me going to Kaggle and downloading a dataset called "Fruit Ripeness: Unripe, Ripe, and Rotten" made by a user named Leftin. In this dataset, there are 39.9 thousand different images in the categories of ripe, unripe, and rotten for each of the three fruits. After I downloaded the dataset, I trained my model for 35 epochs (this took about 2 hours). Then, I tested my model with 3 different images in each category and every single image was classified correct. The model's average confidence was about 97% with many of the fresh and rotten images being in the 99 to 100% range while the unripe images averaged between 70-95% on average. In the end, my model is a really good way for shoppers and farmers to find out whether or not an orange, apple, or banana is ripe, unripe, or rotten, but you can only use it for these fruits in their un-peeled/un-sliced form.




Example of Test: https://drive.google.com/file/d/1q5y-yjTi5U9hMzOvigLitfkGjL1k0t2R/view?usp=sharing 




# Imagenet
For my project, I used a neural network on Jetson-Inference called Image-net. Image-net lets you use the AI to scan images and uses image classification to determine what each object is. Also, for Image-net, what you have to do is train the model to recognize certain things that you want. For me, I did it to recognize whether fruits apple, banana, and orange are ripe, unripe, or rotten.




# Kaggle Dataset
For my project, I downloaded a dataset called "Fruit Ripeness: Unripe, Ripe, and Rotten" by a user named Leftin on Kaggle. This dataset has 39,900 images of ripe, unripe, and rotten fruits. The three fruits in the dataset are apples, bananas, and oranges. I used these images to train my model to recognize whether the fruits were ripe or not.


This is the link for the dataset on Kaggle: https://www.kaggle.com/datasets/leftin/fruit-ripeness-unripe-ripe-and-rotten


[View a video explanation here](video link)




## The Algorithm
To train the model, I ran a command in the docker of Jetson-Inference to prompt the training. This was the command: python3 train.py --model-dir=models/dataset data/dataset. This made the model run through 35 different epochs of every single image in the folder which trained it to recognize whether fruits are unripe, ripe, or rotten


## Running this project


1. Steps for Running this Project.


# Steps
To use my model, you must:


    1. Go to my GitHub post and download my model into VS Code


    2. Enter your image of a banana, apple, or orange into jetson-inference/python/training/classification/data/dataset/test/TestHere


    3. Name your image Test.png(Or jpg or any other image type)


    4. In your terminal, run this command: cd jetson-inference/python/training/classification


    5. Run this command: NET=models/fruitmodel  DATASET=data/dataset


    6. Run this command: imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/TestHere/Test.png(or replace png with any other image type) TestPhoto.jpg


    7. Click your image to see results


