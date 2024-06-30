# Helmet Safety Detection Project Using YOLOv10

## Introduction

This project aims to detect whether workers are wearing helmets in a construction site using the YOLOv10 object detection model. Object detection is a crucial and complex task in computer vision with various applications, including face recognition, license plate recognition, object tracking in videos, and autonomous driving.

## Project Overview

- **Input**: An image.
- **Output**: Coordinates of bounding boxes around workers and helmets.

## Installation and Setup

### 1. Preparing the Programming Environment

This project uses Google Colab as the development environment.

- **Step 1**: Open [Google Colab](https://colab.research.google.com/).
- **Step 2**: Create a new notebook and change the runtime to GPU.

### 2. Installing and Using Pre-trained YOLOv10 Model

#### Cloning YOLOv10 Repository

```bash
!git clone https://github.com/THU-MIG/yolov10

### Installing Required Libraries
%cd yolov10
!pip install -q -r requirements.txt
!pip install -e .

### Downloading Pre-trained Weights
!wget https://github.com/THU-MIG/yolov10/releases/download/v1.1/yolov10n.pt

### Initializing model
from ultralytics import YOLOv10

MODEL_PATH = 'yolov10n.pt'
model = YOLOv10(MODEL_PATH)

### 3. Running Predictions
IMG_PATH = './images/HCMC_Street.jpg'
result = model(source=IMG_PATH)[0]
result.save('./images/HCMC_Street_predict.png')

### test on images
IMG_PATH = './images/HCMC_Street.jpg'
result = model(source=IMG_PATH)[0]
result.save('./images/HCMC_Street_predict.png')


