# Face Mask Detection

*In the month of February 2021, the CDC issued an order ([LINK](https://www.cdc.gov/quarantine/pdf/Mask-Order-CDC_GMTF_01-29-21-p.pdf)) that requires all passengers utilizing public conveyance to wear facemasks. They must wear them before boarding, disembarking, and during the duration of travel. According to the mandate, conveyance operators must use best efforts to ensure that all passengers are wearing a mask. One could imagine that this requires a lot of extra effort on the part of the operators to make these checks.*

In this project, I will design a model to detect if a person is wearing a mask or not. The idea is that a camera could be placed around an entrance point and the model can automatically detect if the person or group walking through are all wearing facemasks.

## Data 

I will be using a dataset from Kaggle ([LINK](https://www.kaggle.com/andrewmvd/face-mask-detection)). The author of this dataset does not go into detail on how this data was acquired. 

The data provided contains images of groups or individuals with respective XML files that contains coordinates and labels (mask or not) for all faces in a particular image. The XML files follow the Pascal VOC data format for object detection.

## Method

Convolutional Neural Networks were originally designed with image processing in mind. After various modifications on the original idea, CNNs have been used with great success for image classification problems. One of the main advantages of using a CNN over other designs is that image preprocessing is much simpler and it has the ability to automatically extract features and learn from them.

For this project, I will be designing a small CNN to detect if a face has a mask worn or not.

## Data Cleaning/Organizing/Preprocessing

1. The faces need to be extracted from the images

Using images with their respective XML file, I extracted all faces from the image dataset. I then stored these faces in two different folders that corresponds to their labels.

2. Resize the images

Before feeding an image to a CNN, they need to be formatted in a certain way:
(# samples, pixel_height, pixel_width, number_of_color_channels)

All images need to have a consistent height, width, and number of color channels. As I was extracting the faces, I was also resizing them to 50x50.
If the original face was too small, making them bigger would produce a blurry image that most likely would not be useful for training. So I set a cutoff point; if a face was smaller than 20x20 it would not be saved for training.

## Design




