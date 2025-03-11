# Land Cover Classification Using Satellite Imagery  

## Technologies Used  
- 🧠 **Machine Learning** (CNN)  
- 🖼 **Image Processing** (RGB Matrix Conversion, Mask Labeling)  
- 🛰 **Satellite Data** (DigitalGlobe)  
- 🏗 **Data Handling** (Large Image Processing)  

## Project Objective  
The objective of this project is to classify and segment the geographic features of a land cover satellite image. Mask images will be produced by coloring the classified image segments with certain colors. The mask image will then serve as a map to show the locations of different geological features within a high-resolution satellite image.  

## Applications in Energy  
This is relevant to the energy industry as the classification task may help identify sub-sections of land that may contain optimal drilling sites for natural resources (oil, gas, etc.) through satellite imagery.  

**Example:** A drilling company wanting to conduct natural gas extraction might need to identify a strategic location to drill to optimize their resource allocation. Classifying certain sub-sections of a satellite image might be useful in narrowing down the best sites, saving both time and money.  

## Dataset  
[Dataset Link]  

The dataset we’re planning on using contains **803 satellite and mask images** that are **2448 x 2448 pixels**. The satellite images have **50cm pixel resolutions** and are collected by **DigitalGlobe’s satellite**. Additionally, the dataset contains **171 validation images** and **172 test images** that do not have corresponding mask images.  

## ML Methodology  

### Image Preprocessing  
In order to create a labeled dataset for classification, we will convert the provided mask image into labeled groups of pixels that correspond to the same pixels on the satellite image. The satellite image will be converted into a **3D matrix** representing the RGB values for each pixel.  

### Model  
We will use a **Convolutional Neural Network (CNN)** to classify subsections of the input **3D matrix of pixels** as a certain land feature. The network will be trained by computing the error in the produced classification versus the labeled classification (derived from the mask image).  

The model’s output will be a **2D matrix** with the same length and width as the original image that stores numbers between **1 and 7**, each denoting what type of land the model believes exists at each pixel of the original image.  

### Postprocessed Output  
Once we have produced the classification for each pixel on the satellite image, we will return an image with a **translucent color overlay**. There will be a **color legend** denoting what type of land corresponds to each color.  
