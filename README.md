<div id="top"></div>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->




<!-- PROJECT LOGO -->
<br />
<div align="center">
  <h3 align="center">DEEP FACE DETECTION</h3>

  <p align="center">
    A computer Vision project to detect human faces in real-time.
    

    
<br/>
    
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#What is VGG16"?What is VGG16?</a>
    </li>
    <li><a href="#VGG16 Architecture">VGG16 Architecture</a></li>
    <li><a href="#Dataset collection, Annotation & Augmentation">Dataset collection, Annotation & Augmentation</a></li>
    <li><a href="#Model Building">Model Building</a></li>
    <li><a href="#Localization loss & classification loss">Localization loss & classification loss</a></li>
    <li><a href="#Performance Plot">Performance Plot</a></li>
  </ol>
</details>



<!-- ABOUT THE Paper -->
## What is VGG16?

A ConvNet is a type of artificial neural network that is also known as a convolutional neural network. An input layer, an output layer, and multiple hidden layers comprise a convolutional neural network. VGG16 is a CNN (Convolutional Neural Network) that is widely regarded as one of the best computer vision models available today. The authors of this model evaluated the networks and increased the depth with a very small (3 *3) convolution filter, which demonstrated a considerable improvement over prior AlexNet. They increased the depth to 16-19 weight layers, resulting in around 138 trainable parameters.
<br/>

## VGG16 Architecture

<img width="650" alt="vgg16" src="https://github.com/stuck-in-a-local-optimum/deep-face-detection/blob/main/images/vgg16.png">
<br/>

* The 16 in VGG16 refers to 16 weighted layers. VGG16 comprises thirteen convolutional layers, five Max Pooling layers, and three Dense layers in total, for a total of 21 layers, but only sixteen weight layers, i.e., learnable parameters layers.


<img width="650" alt="vgg16_layers" src="https://github.com/stuck-in-a-local-optimum/deep-face-detection/blob/main/images/vgg16_layers.png">

* The input tensor size for VGG16 is 224, 244 with 3 RGB channels.

* The most striking feature of VGG16 is that, rather than having a huge number of hyper-parameters, they focused on having convolution layers of 3x3 filter with stride 1 and always used the same padding and maxpool layer of 2x2 filter with stride 2.
* Conv-1 Layer has 64 filters, Conv-2 Layer has 128 filters, Conv-3 Layer has 256 filters, Conv 4 and Conv 5 Layers have 512 filters.
* Three Fully-Connected (FC) layers follow a stack of convolutional layers: the first two have 4096 channels each, the third performs 1000-way ILSVRC classification and thus contains 1000 channels (one for each class). The final layer is the soft-max layer.
* After a stack of convolutional layers, three Fully-Connected (FC) layers are added: the first two have 4096 channels each, while the third performs 1000-way  classification and so has 1000 channels (one for each class). The soft-max layer is the final layer.

## Dataset collection, Annotation & Augmentation

* Using the openCV library, we collected 90 images from our computer's camera, both with and without faces.
* The images were then annotated and labelled with the [labelMe](https://github.com/wkentaro/labelme) annotation tool.
* Because Neural Networks require large amounts of data to be trained properly, and thus 90 images are insufficient, we employed image augmentation to create new samples from our existing samples by making the following changes to our existing samples using [Albumentations](https://albumentations.ai/docs/) tool:
    * RandomCrop
    * HorizontalFlip
    * RandomBrightnessContrast change
    * RandomGamma
    * RGBShift
    * VerticalFlip

## Model Building 

<img width="650" alt="build_model" src="https://github.com/stuck-in-a-local-optimum/deep-face-detection/blob/main/images/build_model.png">

* Because our goal is to categorise the image as a face-image and also draw a boundary box around the face so we removed the top-layers of vgg-16 since they for classification purpose.
* Then we added our classication layer of 1 neuron with sigmoid activation function for face detection and a regressor layer of 4 neurons for boundary point value.




## Localization loss & classification loss

<img width="650" alt="loss" src="https://github.com/stuck-in-a-local-optimum/deep-face-detection/blob/main/images/loss.png">


## Performance Plot

<img width="650" alt="performance_plot" src="https://github.com/stuck-in-a-local-optimum/deep-face-detection/blob/main/images/preformance_plot.png">






<!-- CONTACT -->
## Contacts
[LinkedIn](https://www.linkedin.com/in/ajeet-yadav-a507971a9/)
<br/>
[Twitter](https://twitter.com/weightsNbiases)



<p align="right">(<a href="#top">back to top</a>)</p> 

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

