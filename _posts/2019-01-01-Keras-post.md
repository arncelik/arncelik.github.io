---
layout: post
title: "Notebook : Introduction to Keras"
date: 2019-02-01
excerpt: "Keras Basics"
tags: [keras, tensorflow, machine learning, deep learning]
feature: https://miro.medium.com/max/1000/1*LkKz4wtZNBo5i-Vc8DWhTA.png
comments: true
---
# What is Keras?
Let's take a look at the definition of Keras before moving on to explanation of my first task of "Machine Learning Practice" project.
## Definition:

Keras is a high-level neural networks API, written in Python. It's capable of running on top of TensorFlow.
You may want to use Keras if you want to quickly build and test a neural network with minimal lines of code. It also;

* Supports both convolutional networks and recurrent networks, as well as combinations of the two.
* Runs impeccable on CPU and GPU.

The core data structure of Keras is a model, a way to organize layers. The simplest type of model is the Sequential model, a linear stack of layers.

# Machine Learning Practice Task 1: LeNet Implementation with Keras

In this task I have worked on image classification using Keras library and LeNet on the MNIST dataset. I am pretty beginner in Deep Learning, so it was new to me working with Keras and LeNet. I have searched for the resources to see examples before coding right away.Then I encountered this tutorial [LeNet-Convolutional Neural Network in Python](https://www.pyimagesearch.com/2016/08/01/lenet-convolutional-neural-network-in-python/).It is well explained and a brief post that helped me a lot to get the logic of the algorithm.

What was my main task was training the model, and writing a script to test some images from validation dataset.
After importing necessary libraries,  I used build method that takes following parameters:
* width
* height
* depth
* number of classes (unique number of clas labels) in the MNIST dataset.


~~~python
# import the necessary packages
from keras.models import Sequential
from keras.layers.convolutional import Conv2D
from keras.layers.convolutional import MaxPooling2D
from keras.layers.core import Activation
from keras.layers.core import Flatten
from keras.layers.core import Dense
from keras import backend as K

class LeNet:
	@staticmethod
	def build(numChannels, imgRows, imgCols, numClasses,
		activation="relu", weightsPath=None):
~~~
After initializing the model, we can start adding layers to it, next move will be compiling and fitting the model.
