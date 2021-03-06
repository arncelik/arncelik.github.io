# Notebook 2: U-Net

### Introduction

U-Net is another architecture type of CNN.Its name comes from the shape of its architecture which will be discussed in this post.

U-Net was designed especially for medical image segmentation which is partitioning an image into multiple sections/segments.It's aim is to predict each pixel's class.

I stopped there and asked what is the image segmentation is and at this point I thought is an abstruse topic yet I could not map the architecture in my mind, so I kept reading and then I came across this statement which made everything crystal clear:

**"In simple terms, they refer to pixel-level labelling i.e. each pixel in an image is provided with a class label. You get segmentation maps."**

* The main idea behind U-Net is to learn the feature mapping of an image and exploit it to make more distinct feature mapping. It happens in three steps:
- Classifying the image entirely
- Segregation the image in groups
- Classifies the segments/portions

First, the image data needed to be converted into vector in order to perform classification. In image segmentation, we only need to convert feature map into a vector but also reconstruct the image from this vector.

### Architecture

![UNet Architecture](https://miro.medium.com/max/3110/1*lvXoKMHoPJMKpKK7keZMEA.png)

The architecture is in "U" shape, so it vindicates it's name.
There are two major parts:

#### Left side(Contracting):
This part is known as contracting part which follows a typical Convolutional Network, but with repetitons.
**It consists two 3x3 convolutions and a 2x2 max pooling layer.**

#### Right side (Expansion):
We crop the image. Cropping is a must since the loss of border pixels in every convolution. We have an unsampling of the feature map and a 2x2 convolution that decreases the size of the image by half.

![UNet](https://neurohive.io/wp-content/uploads/2018/11/u-net-x.png)

#### Final Layer:
* 1x1 convolutuion is used to map each component feature vector to the desired number of classes.
* It has 23 convolutional layers in total.

### Advantages
- Computationally effective
- Does not require big data to train the model, small data would be enough.
- Trained end-to-end
- Suitable for biomedical data

Visit my ongoing project [Lung tumor detection using CNN](https://github.com/arncelik/Lung-Cancer-Detection) to see an example.
