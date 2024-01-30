# OCR Pipeline
The OCR pipeline has three stages:  In the first stage we use a dataset of digital invoices to train the YOLO object detection model to identify three essential classes from the invoices: Invoice number, Billing Date, and Total amount. After that, we will use Tesseract for performing OCR in python.

#### Application
Any person currently identifying object classes from images manually to be used as labels for data source can use this pipeline.

#### Tech Stack
Language: Python
Object detection: YOLO V4
Text Recognition: Tesseract OCR
Environment: Google Colab

## Quick Start - OCR Text Prediction

For object class detecion using Yolo, you can use this [Google Colab notebook](https://colab.research.google.com/drive/1ZyBmjOZRf2ZmNDUOelXYbaznWDB4MV7l)

For image labelling, you can use [Label Studio](https://github.com/HumanSignal/label-studio#readme) to label audio, text, images, videos, and time series data types for export to various model formats. See the [setup instructions](https://github.com/HumanSignal/label-studio#install-for-local-development)
(Note [labellmg-master](https://github.com/dollja/OCR-text-prediction/labellmg-master) is now maintained in Label Studio)

For OCR using Tesseract and Yolo, see [tesserract-training](https://github.com/dollja/OCR-text-prediction/tesseract_training)

## Part I: Set up Python for OCR
Step-by-step guide to build Python OCR
 
1.	Set up and install to run Yolov4
Download AlexeyAB's repository and adjust the Makefile to enable OPENCV and GPU for darknet and then build darknet.
2.	Download pre-trained YOLOv4 weights
YOLOv4 has already been trained on the coco dataset, with 80 classes that it can predict. We will take these pre-trained weights to understand how they result in some test images.
3.	Create display functions to display the predicted class.
Use OpenCV for visualizing object detection results of the YOLO model.
4.	Data collection and Labeling with LabelImg
This YOLO OCR project aims to train YOLO to learn three new classes; You can use Labellmg tool to create a new dataset for training and validation.  Labellmg is the tool that is used to annotate the image with three classes, and YOLO will then use these annotations during training.
5.	Configuring Files for Training - This step involves configuring custom .cfg, obj.data, obj.names, train.txt and test.txt files.
- Configuring all the needed variables based on class in the config file
- Creating obj.names and obj.data files

                        1. obj.names: Classes to be detected (image.png)
 
 
                      
                         2. obj.data: image.png
 
 
 - Configuring train.txt and test.txt
6.	Download pre-trained weights for the convolutional layers
YOLO's object detection model has already been trained on the COCO dataset for 80 different classes. You can download the weights and then fine-tune them accordingly with the help of their custom dataset. The model can learn and adapt to the new classes with just a few new data points.
7.	Training Custom Object Detector
8.	Evaluating the model using Mean Average precision
9.	Predict image classes and save the coordinates separately
10.	Detecting text from the predicted class
o	Importing pytesseract and setting environment variable (for windows only, for Unix it is already set) for English trained data
- Getting the list of predicted files from the directory
 - Using tesseract pre-trained LSTM model to extract the text
 - Fine-tuning the LSTM model. (Please note that fine-tuning the model will only be required if the extracted text is inaccurate to that shown in the image)
## Part II Train Tesseract OCR in Python
Follow the below steps to train Tesseract-OCR in Python:
1.	Install Tesseract from the website Home · UB-Mannheim/tesseract Wiki · GitHub.
2.	Use jTessBoxEditor for merging train data to .tiff format.
3.	Generate .box files from the .tff files to create the training dataset.
4.	Use the above dataset for training the algorithm.


### How to Install Tesseract OCR in windows python? 
Visit the website https://github.com/UB-Mannheim/tesseract/wiki#tesseract-at-ub-mannheim and download the windows installer for tesseract depending on whether your system is 32-bit/64-bit. After that, run the downloaded file and wait until the system extracts all the necessary files. Click on ‘Next’ and accept the license agreement to install. If you are interested in OCR for languages other than English, tick the additional language tools box and select the language of your choice. After that, click on the ‘Next’ button and wait for the installation process to get over. Finally, click on ‘Finish’ to complete the installation process.

## Tools and Techniques 
#### OpenCV
OpenCV is a popular computer vision and image processing libraries. This pipeline uses OpenCV to process the images before serving them to the object detection model YOLO. Additionally, we will use various functions of the OpenCV library for visualizing the testing results of the YOLO model.
#### Google Colab
The Google Colab application provides ease-of-use and efficiency to people building executable programs in Python. This project uses Colab notebooks to implement the complete solution. We will link the darknet OCR framework for training the YOLO v4 model using GPU for faster execution.
#### YOLOv4
YOLO v4 is an object detection model developed by Alexey Bochkovskiy, Chien-Yao Wang, and Hong-Yuan Mark Liao where YOLO stands for ‘You only look once’. 


