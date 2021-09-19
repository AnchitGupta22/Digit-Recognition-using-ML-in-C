# Digit-Recognition-using-ML-in-C
This project aims to recognise handwritten digits using machine learning in C language. Its a beginner's attempt to create a simple neural network, and its underlying mathematics, in C
language to solve a classification problem.

## Table of Content

1. [Concepts used](#1-concepts-used)

2. [Input data](#2-input-data)

3. [Flowchart](#3-flowchart)

4. [Working](#4-working)

5. [Output](#5-output)

6. [Improvements](#6-improvements)

7. [System specs.](#7-system-specifications)

## 1. Concepts used

(i) Artificial Neural Network. The current system uses a basic ANN without any hidden layer. The structure is described below :-

![ann](https://github.com/AnchitGupta22/Digit-Recognition-using-ML-in-C/blob/master/asset/structure_of_ann.PNG)

The input layer comprises of 784 neurons, since the size of each image in the dataset is 28x28. The output layer has 10 neurons followed by a softmax classfier to generate a single
final output for the input image.

(ii)  Graph creation in C using graphics.h 

## 2. Input data

This project utilizes the widely popular MNIST handwritten digit dataset. The [MNIST database](http://yann.lecun.com/exdb/mnist/) of handwritten digits has a training set of 60,000 
examples, and a test set of 10,000 examples. It is a subset of a larger set available from NIST. The digits have been size-normalized and centered in a fixed-size image. 
It is a good database for people who want to try learning techniques and pattern recognition methods on real-world data while spending minimal efforts on preprocessing and formatting. 

## 3. Flowchart

Below is the flowchart for the entire project :-

![flowchart](https://github.com/AnchitGupta22/Digit-Recognition-using-ML-in-C/blob/master/asset/flowchart_minor1.PNG)

## 4. Working

(i) The data is read using ```mnist_get_dataset()```. This function is present [here](https://github.com/AnchitGupta22/Digit-Recognition-using-ML-in-C/blob/master/mnist_file.c#L144) 
and reads both the training and testing sets.

(ii) Next we initialise the weights and biases with random values using ```neural_network_random_weights()``` which can be found [here](https://github.com/AnchitGupta22/Digit-Recognition-using-ML-in-C/blob/master/neural_network.c#L17).

(iii) We then calculate the number of batches we will be creating using a very simple formula, **size of dataset/size of a single batch**. Here, the size of a single batch is 
taken to be 100.

(iv) Set-up the graphics.h library and generate the background of our graph, including most of the axes and labels.

(v) Start a clock timer.

(vi) This step includes the main working of our network. We perform the below steps in a loop for 100 Epochs.

   a. Initialise a new batch on the training dataset.
    
   b. Run one step of gradient descent and calculate the loss. The learning rate of 0.5 is taken for training. 
    
   c. Calculate the accuracy for this epoch using the entire test dataset.
    
   d. Plot this accuracy on the graph. Also, add this accuracy value in an accuracy matrix for later use which will be discussed in later steps.
      
(vii) Stop the clock timer. Calculate the total time taken for step (vi).

(viii) Calculate the maximum accuracy value and average accuracy value using the accuracy matrix from step (vi) d.

(ix) Plot the total time taken to run step (vi), maximum and average accuracy on the graph.

(x) Free all the pointers.

## 5. Output

Following is the graph generated in real-time while execution (the gif is an accelerated version) :-

![output](https://github.com/AnchitGupta22/Digit-Recognition-using-ML-in-C/blob/master/asset/output.gif)

## 6. Improvements

(i) Values in the batch can be more randomised.

(ii) A hidden layer can be added to improve the accuracy.

## 7. System specifications

(i) Ubuntu 16.04 on a VM

(ii) 1 GB RAM

(iii) libgraph for running graphics.h on ubuntu
    
    
