# Image_Captioning_Project

Image Captioning Project from Coursera.
In this project we will define and train an image-to-caption model, that can produce descriptions for real world images!

<img src="https://github.com/hse-aml/intro-to-dl/blob/master/week6/images/encoder_decoder.png?raw=1" style="width:70%">

Model architecture: CNN encoder and RNN decoder.(https://research.googleblog.com/2014/11/a-picture-is-worth-thousand-coherent.html)

**Encoder**: We will use pre-trained InceptionV3 model for CNN encoder (https://research.googleblog.com/2016/03/train-your-own-image-classifier-with.html) and extract its last hidden layer as an embedding:
<img src="https://github.com/hse-aml/intro-to-dl/blob/master/week6/images/inceptionv3.png?raw=1" style="width:70%">

**Decoder**: The decoder part of the model is using a recurrent neural networks and LSTM cells to generate the captions.
<img src="https://miro.medium.com/max/700/0*xouGPXQYGad-e4T3" style="width:70%">

Since our problem is to generate image captions, RNN text generator should be conditioned on image. The idea is to use image features as an initial state for RNN instead of zeros. 
During training we will feed ground truth tokens into the lstm to get predictions of next tokens.(http://cs.stanford.edu/people/karpathy/):

<img src="https://github.com/hse-aml/intro-to-dl/blob/master/week6/images/encoder_decoder_explained.png?raw=1" style="width:50%">

## Dataset

<img src="https://miro.medium.com/max/534/1*CNk55KpPjeK12qVGZ1xZxA.png" width="45%" height="45%">
The dataset is a collection of images and captions. Here, it’s the COCO dataset. For each image, a set of sentences (captions) is used as a label to describe the scene.
Ralavent Links:

- train images http://msvocds.blob.core.windows.net/coco2014/train2014.zip
- validation images http://msvocds.blob.core.windows.net/coco2014/val2014.zip
- captions for both train and validation http://msvocds.blob.core.windows.net/annotations-1-0-3/captions_train-val2014.zip


## Results
Following are a few results obtained after training the model for 12 epochs.

Image | Caption 
--- | --- 
<img src="https://github.com/adityaj3/Image_Captioning_Project/blob/main/Output/download%20(1).png" width="400"> | **Generated Caption:** a close up of a laptop computer on a desk
<img src="https://github.com/adityaj3/Image_Captioning_Project/blob/main/Output/download%20(2).png" width="400"> | **Generated Caption:** a elephant is standing in the dirt next to a fence
<img src="https://github.com/adityaj3/Image_Captioning_Project/blob/main/Output/download.png" width="400"> | **Generated Caption:** a baseball player swinging a bat at a ball
<img src="https://github.com/adityaj3/Image_Captioning_Project/blob/main/Output/download%20(3).png" width="400"> | **Generated Caption:** a group of people standing around a boat on a river
<img src="https://github.com/adityaj3/Image_Captioning_Project/blob/main/Output/download%20(4).png" width="400"> | **Generated Caption:** a man sitting at a table with a laptop computer
<img src="https://github.com/adityaj3/Image_Captioning_Project/blob/main/Output/download%20(5).png" width="400"> | **Generated Caption:** a group of people sitting on a couch playing video games
