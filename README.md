# OCR-text-prediction


## Quick Start
For object class detecion using Yolo, you can use this [Google Colab notebook](https://colab.research.google.com/drive/1ZyBmjOZRf2ZmNDUOelXYbaznWDB4MV7l)

For image labelling, you can use [Label Studio](https://github.com/HumanSignal/label-studio#readme) to label audio, text, images, videos, and time series data types for export to various model formats. See the [setup instructions](https://github.com/HumanSignal/label-studio#install-for-local-development)
(Note [labellmg-master](https://github.com/dollja/OCR-text-prediction/labellmg-master) is now maintained in Label Studio)

For OCR using Tesseract and Yolo, see [tesserract-training](https://github.com/dollja/OCR-text-prediction/tesseract_training)

# OCR Pipeline Project Overview
The OCR pipeline has three stages:  In the first stage we use a dataset of digital invoices to train the YOLO object detection model to identify three essential classes from the invoices: Invoice number, Billing Date, and Total amount. After that, we will use Tesseract for performing OCR in python.

### Application
Any person currently identifying object classes from images manually to be used as labels for data source can use this pipeline.

### Tech Stack
Language: Python
Object detection: YOLO V4
Text Recognition: Tesseract OCR
Environment: Google Colab

## OCR Pipeline Tools and Techniques 
### Computer Vision using OpenCV
OpenCV is a popular computer vision and image processing libraries. We will use OpenCV to process the images before serving them to the object detection model YOLO. Additionally, we will use various functions of the OpenCV library for visualizing the testing results of the YOLO model.
### Coding with Google Colab
The Google Colab application provides ease-of-use and efficiency to people building executable programs in Python. This project uses Colab notebooks to implement the complete solution. We will link the darknet OCR framework for training the YOLO v4 model using GPU for faster execution.
### Text Detection using YOLO
YOLO v4 is an object detection model developed by Alexey Bochkovskiy, Chien-Yao Wang, and Hong-Yuan Mark Liao where YOLO stands for ‘You only look once’. 


