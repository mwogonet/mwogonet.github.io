---
title: Semantic Segmentation using ENet
date: 2018-05-29
categories:
  - Training process
image: https://mwogonet.github.io/images/accuracy.JPG
author_staff_member: Cynthia,Gloria
---

We trained a machine learning algorithm on various classes such as Cassava Mosaic Disease(CMD), Cassava Bacterial Blight(CBB), Cassava Brown Streak Disease(CBSD), Cassava Green Mite(CGM) and Healthy images. The steps performed during this process include the following;

<b>Step one</b>: We defined the structure of our files. These image files were stored in the cropped and uncropped folders. Within these folders, we had a folder for each disease and healthy images. Within the different disease folders, we had the severities for each disease.<br/>

<b>Step two</b>: We made different partitions of files which were included in the label dictionary(key,value). The label_dictionary is an object where the keys are the different disease labels and the values are the list of directories.<br/>

<b>Step three</b>: Compilation.This was done before training the model. We had to configure the learning process which was done via the compile method.It receives three arguments such as the optimizer, the loss function and the list of metrics.<br/>

<b>Step four</b>:Start training.For training, we used the fit function.The arguments within this function included;  

1. epochs:An epoch is one complete iteration over all of the training dataset.<br/>

2. batch_size:Number of samples that are going to be propagated through A network.<br/>

3. steps_per_epoch: This is defined by (Number of Samples//batch_size)<br/>

4. validation_steps:(Samples of the Validation dataset//batch_size)<br/>

5. class_weight:The class_weight parameter of the fit() function is a dictionary mapping classes to a weight value.<br/>

6. validation_data: This is data that is used for testing.<br/>

7. callbacks:used to get internal view on internal states and statistics of model during training.These are mainly because of an early stop or a checkpoint. The early stop is done when a monitored quantity has stopped improving.The checkpoint is done to moitor progress.<br/>

During the training process, we made a comparison between both the cropped images and uncropped images to find out which produced a better validation accuracy.<br/>

The images were passed through the ENet algorithm which performed semantic segmentation on the cassava images as illustrated below so as to remove the background noise and improve on the accuracy.<br/>

<p><b>Good segmentation </b></p>
<img src="https://mwogonet.github.io/images/good.jpg" width="400" height="500"/>

<p><b>Poor segmenatation </b></p>
<img src="https://mwogonet.github.io/images/poor.jpg" width="400" height="500"/>




