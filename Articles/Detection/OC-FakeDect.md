Title: OC-FakeDect: Classifying Deepfakes Using One-class Variational Autoencoder
# Info
Classification
- anomaly
- one-class
**Publication**:
- 2020
**differential**:
- 
**no-reference**:
- 
**Datasets**:
- 
**performance**:
- Precision, Recall and F1
![[Pasted image 20231002144605.png]]
**attacks**:
- 
**Motivation(if relevant)**
- However, binary-classification based methods generally require a large amount of both real and fake face images for training, and it is challenging to collect sufficient fake images data in advance. 
- Besides, when new deepfakes generation methods are introduced, little deepfakes data will be available, and the detection performance may be mediocre.
- To overcome these data scarcity limitations, we formulate deepfakes detection as a one-class anomaly detection problem.
**Proposal(brief)**:
- We propose OC-FakeDect, which uses a one-class Variational Autoencoder (VAE) to train only on real face images and detects non-real images such as deepfakes by treating them as anomalies
- which is based on a one-class Variational Autoencoder (OC-VAE) with an additional encoder structure [18] for training only on normal data
- We propose a one-class classification model OC-FakeDect, based on Variational Autoencoder (VAE) for detecting Deepfakes as an anomaly detection problem
**Method(long)**:
- 
![[Pasted image 20231002144501.png|]]
**remarks**
- Current facial manipulation methods can be broadly categorized into the following categories: 1) Facial expression manipulation [25], in which one can transfer facial expressions of a person to another using a method such as Face2Face [31], and 2) identity manipulation based on face swapping methods, in which one can replace a person’s face with that of another person.
- One-class Support Vector Machine (OC-SVM) [26], which is a particular case of support vector machine that separates data points from the origin by learning a hyper-plane in a Reproducing Kernel Hilbert Space (RKHS) [36] and maximizing RKHS distance, is one of the most popular unsupervised learning methods that can detect anomalies. However, the application of non-parametric OC-SVM to the detection of deepfakes can lead to a high error rate with many support vectors.
- Another example of a one-class-based approach has been explored by Oza and Patel [22], who proposed One-class Convolutional Neural Network (OC-CNN). The main idea of OC-CNN is to use a zero centered Gaussian noise in the latent space as the negative class and train the network using the cross-entropy loss. Their core objective is to make all negative distributions close to the hyper-plane. However, the objective of this model differs from the main objective of ours, because their model trains on negative or “abnormal” class with standard cross-entropy loss, while our model focuses on the “normal” class only.
- Autoencoders (AEs) can also be used for one-class classification [1], or anomaly detection. An AE can be trained to reconstruct the input with a low reconstruction error rate by learning latent features of an input image. Here, “normal” data can be used for training and “abnormal” data can be detected by using reconstruction error as the anomaly score. However, AEs are deterministic and discriminative models without a probabilistic foundation
- To further improve AE, Variational Autoencoder (VAE) [18], which is a stochastic generative model that can provide calibrated probabilities, has been proposed and has shown to yield better fake image detection performance. In this work, we apply OC-FakeDect to demonstrate an enhanced detection performance compared to that of AE.
**references to detection methods**
- Hsu et al. [11] presented a two phase deep-learning approach for the detection of several GAN-based deepfake images
**references to localization manipulation methods**
- 
**references to manipulations**
- Methods like Adobe Photoshop, StyleGAN [15], Faceswap, PGGAN [14], and diverse high-fidelity images with VQ-VAE-2 [24] can be used to create fake images.
# PDF 