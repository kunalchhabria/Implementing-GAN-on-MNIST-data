# GAN-auto-write
Generative Adversarial Network that learns to generate handwritten digits. Trained on the MNIST dataset. I have made this repository solely for learning GAN's and their working mechanism. Thanks to all the online materials available, O'Reilly Network and yes Ian Goodfellow.

## Requirements and installation
In order to run [auto_write.ipynb](auto_write.ipynb) , you'll need **[TensorFlow](https://www.tensorflow.org/install/) version 1.0 or later** and [NumPy](https://docs.scipy.org/doc/numpy/user/install.html). You'll additionally need [Jupyter](https://jupyter.readthedocs.io/en/latest/install.html) and [matplotlib](https://matplotlib.org/).

## Dataset
We'll be using [MNIST](http://yann.lecun.com/exdb/mnist/) dataset here, a benchmark dataset in deeplearning. It consists of 70,000 images of handwritten digits compiled by the U.S. National Institute of Standards and Technology from Census Bureau employees and high school students.

The data is provided here in the MNIST_data folder. Or if you want you can get it from the link above.

## GAN Architecture
Generative adversarial networks consist of two models: a generative model and a discriminative model.
![GAN Architecture](https://github.com/aalind0/GAN-auto-write/blob/master/images/architecture.png "GAN Architecture")

The discriminator model is a classifier that determines whether a given image looks like a real image from the dataset or like an artificially created image. This is basically a binary classifier that will take the form of a normal convolutional neural network (CNN).

The generator model takes random input values and transforms them into images through a deconvolutional neural network.
Over the course of many training iterations, the weights and biases in the discriminator and the generator are trained through backpropagation. The discriminator learns to tell "real" images of handwritten digits apart from "fake" images created by the generator. At the same time, the generator uses feedback from the discriminator to learn how to produce convincing images that the discriminator can't distinguish from real images.

## GAN Superpowers - 
Here comes my favourite part about training GAN's. GAN's have two loss functions: one that encorages the generator to make better and better images and the other that encourages the discriminator to distinguish generated images form the real images.

Thus both the generator and the discriminator are being trained simultaneously. Now as the disciminator gets better and better at distinguishing the real images form the generated images, the generator is able to better tune its weights and biases to create more and more convincing images of handwritten text.

## Some results - 

1. Sample image from MNIST dataset. We have to obtain an image similar to this from our trained generator.

   ![](https://github.com/aalind0/GAN-auto-write/blob/master/images/mnist.png "MNIST sample")

2. Image from our untrained generator.

   ![](https://github.com/aalind0/GAN-auto-write/blob/master/images/untrained.png "Untrained image")

3. Image after training the generator.

   ![](https://github.com/aalind0/GAN-auto-write/blob/master/images/four.png) ![](https://github.com/aalind0/GAN-auto-write/blob/master/images/six.png)  ![](https://github.com/aalind0/GAN-auto-write/blob/master/images/nine.png)
   
   The images generated by the trained generator are much similar to the handwritten text thus proving that GAN's can be used to create synthetic data similar to some known input data.

## Some GIF's of the process - 

   ![](https://github.com/aalind0/GAN-auto-write/blob/master/images/trans3.gif "Transaction")  ![](https://github.com/aalind0/GAN-auto-write/blob/master/images/trans4.gif "Transaction")
    
   During training it gradually refines it's ability to generate digits.
