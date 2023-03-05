# ESRGAN
This repository contains my Pytorch implementation of ESRGAN (Enhanced Super Resolution Generative Adversarial Networks).

## Overview

Super resolution is a task of estimating a high resolution image from a low resolution image. This estimated image is called as super resolved image. Previous methods included optimization target for mean squared error (MSE) and maximization of peak signal to noise ratio (PSNR) which are defined pixel wise. 

SRGAN is a GAN based network which is structurally similar to 16 blocks deep ResNet, and the paper which proposed SRGAN also proposed a new perceptual loss which consists of an adversarial loss and a content loss (reconstruction loss). In the adversarial loss, we compute the MSE in the feature space instead of the pixel space, i.e, for a specific layer within VGG, we want their features to be matched. 

As the name suggests, ESRGAN is an enhanced version of SRGAN, that is, the overall high level architecture of ESRGAN is the same as SRGAN with mainly three improvements: 

## Network Architecture

The network structure of ESRGAN is improved by removing all the batch normalization layers, and introducing the RRDB (Residual in-Residual Dense) blocks, which results in a more deeper and complex structure for the generator network than the original residual block in SRGAN. 

## Adversarial Loss

The adversarial loss is improved further with the concept of relativistic average GAN, where instead of the standard discriminator giving the probability that an image is real or fake, relativistic discriminator predicts whether the real image is relatively more realistic than the fake image. 

## Perceptual Loss

The perceptual loss is improved in ESRGAN by using the features before activation, and is implemented by using VGG features before activation instead of after activation as in SRGAN. 

## Train ESRGAN model

To train this model, use

``` bash
    python -m train
```











