# Super-Resolution Generative Adversarial Network (SR-GAN)

This repository contains an implementation of a **Super-Resolution Generative Adversarial Network (SR-GAN)** using **PyTorch**. SR-GAN enhances image resolution by generating high-quality images from low-resolution inputs. The model is trained on the **ImageNet dataset** to demonstrate its functionality and performance.


## Introduction

The objective of this project is to build an SR-GAN capable of improving image resolution through a generator-discriminator framework, following the original design proposed in the SR-GAN paper.

## Model Architecture

The SR-GAN architecture comprises:

- **Generator**: Upscales low-resolution images to high-resolution ones. It consists of several convolutional layers, upsampling layers, and residual blocks, incorporating **PReLU** and **LeakyReLU** activation functions to introduce non-linearity.

- **Discriminator**: Distinguishes between real high-resolution images and those generated by the Generator. Built on a convolutional layer followed by a fully connected layer, it uses LeakyReLU activation in its convolutional blocks.

## Loss Functions

- **VGG Loss**: Computes the mean squared error between features extracted by a pre-trained VGG19 network from the generated and target high-resolution images, ensuring that the generated features are comparable to those of the target images.

- **Binary Cross-Entropy (BCE) Loss**: Used for training the Discriminator by measuring the discrepancy between actual and predicted distributions of real and generated images.

## Training Process

The model was trained for **1000 epochs** on the ImageNet dataset. The **Adam optimizer** was utilized with a learning rate of **0.0002** and momentum parameters (betas) of **(0.5, 0.999)** for both the Generator and the Discriminator. The training loop alternated between optimizing the Generator and the Discriminator.

## Results

After training for 1000 epochs, we observed a decrease in losses for both the Discriminator and Generator, indicating improved performance. Sample output images are provided below.

## Figures
<img width="468" alt="image" src="https://github.com/user-attachments/assets/47e82499-00e0-4fa6-9424-1877d14979db">

 **Figure 1**: SR-GAN Architecture 
  
- <img width="499" alt="image" src="https://github.com/user-attachments/assets/8e9a3ee8-2d25-4ad6-87f7-45c562a54dfe">
 **Figure 3**: Output after 50 epochs.
  
- <img width="471" alt="image" src="https://github.com/user-attachments/assets/03a27bbc-7fcf-48ee-a017-0fa057248ced">
 **Figure 4**: Output after 500 epochs.
  
- <img width="485" alt="image" src="https://github.com/user-attachments/assets/8188d69e-9fff-44a8-860b-6811fcedc59e">
 **Figure 5**: Output after 1000 epochs.
  
- <img width="468" alt="image" src="https://github.com/user-attachments/assets/f82625e3-dbf9-4423-9cb6-a0cf5f5204fc">
 **Figure 6**: Sample output on test images.

## References

- [SRGAN Paper](https://arxiv.org/abs/1703.10524) (Link to the original paper for further reading)
