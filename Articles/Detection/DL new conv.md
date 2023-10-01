Title: A Deep Learning Approach To Universal Image Manipulation Detection Using A New Convolutional Layer
# Info

**Publication**:
- 2016
Classification
- binary: in the form of binary classifier for each attack and multi-class classification for all at the same time
**differential**:
- NO
**no-reference**:
- YES
**Datasets**:
- Our experimental image datasets have been collected from 12 different camera models and devices with no previous tampering or preprocessing. 
- We created a set of grayscale images by retaining only the green color layer from each image. 
- We cropped each original image in the center, then subdivided it into 256 × 256 blocks. 
- More explicitly, every block corresponds to a new image that has its corresponding different tampered images.
- In total we created a set of 261,800 unaltered blocks. 
- Next, we generated a set of altered images. We did this by applying the following operations to a set of unaltered image:
	- Median Filtering with a 5 × 5 kernel. 
	- Gaussian Blurring with a 5 × 5 kernel and a standard deviation σ = 1.1. 
	- Additive White Gaussian Noise (AWGN) with standard deviation 2. 
	- Resampling (resizing) using bilinear interpolation and a scaling factor 1.5. 
- We then cropped these images into 256 by 256 blocks to create a total of 333, 200 manipulated blocks. 
- During training and testing all the blocks are further cropped to 227 by 227 blocks.

**performance**:
- binary, i.e. one classifier for each attack 
  ![[Pasted image 20230929113147.png|600]]
  - for every binary classifier we have a total number of 87, 000 blocks for training and 32, 000 blocks for testing.
- for multi-class
![[Pasted image 20230929113317.png|610]]
- we have a total number of 87, 000 blocks for training and 32, 000 blocks for testing
- NOTE they do not mention how accuracy is computed 

**attacks**:
- Digital: median filtering, Gaussian blurring, Additive White Gaussian Noise, Resampling(resizing)
**Motivation(if relevant)**
- significant interest has arisen in the development of universal forensic algorithms capable of detecting many different image editing operations and manipulations.
- In their current form, convolutional neural networks will learn features that capture an image’s content as opposed to manipulation detection features.
- While the development of targeted editing detectors has led to many important advances in information forensics, this approach to image authentication suffers an important drawback: Since a forger has many editing operations at their disposal, a forensic investigator must apply a large number of forensic tests to determine if and how an image has been edited.
- there has been significant interest in the development of universal forensic algorithms designed to detect many, if not all, editing operations.
- While these techniques show great promise, they each learn detection features from pre-selected models
- Direct answer to [[Median filtering]] :
	- *In their experiments, Chen et al. found that the CNN was not able to learn median filtering detection features if images are directly fed to the input layer. Instead, they first extracted a high dimensional feature set from the image known as the median filter residual, then provided this to the input layer of the CNN.*
	- *To overcome this problem, we propose a new form of convolutional layer that will force the CNN to learn manipulation detection features from images without requiring any preliminary feature extraction or pre-processing.*
**Proposal(brief)**:
- . To overcome this issue, we develop a new form of convolutional layer that is specifically designed to suppress an image’s content and adaptively learn manipulation detection features.
- In this paper, we propose a universal forensic approach to performing manipulation detection using deep learning. 
- Specifically, we propose a new convolutional network architecture capable of automatically learning manipulation detection features directly from training data.
- Through a series of experiments, we demonstrate that our proposed approach can automatically learn how to detect multiple image manipulations without relying on pre-selected features or any preprocessing.
- we propose a new universal approach for performing image editing detection that is capable of automatically learning traces left by editing.
**Method(long)**:
- we make use of tools from deep learning known as convolutional neural networks (CNNs).
- Though CNNs are able to adaptively learn good features for object recognition, they are not well suited for performing image manipulation detection in their existing form. 
	- Instead of learning filters that identify traces left by editing and manipulation, the convolutional layers will extract features that capture an image’s content.
	- This effect has recently been observed by Chen et al. during their efforts train a CNN to perform median filtering detection [2]
- In this paper, we propose a new form of convolutional layer designed to suppress an image’s content and adaptively learn manipulation detection features. 
- Using this new convolutional layer, we propose a CNN architecture capable of automatically learning how to detect multiple image manipulations without relying on pre-selected features or models.
- The key idea behind developing this layer is that certain local structural relationships exist between pixels independent of an image’s content. 
	- Manipulations will alter these local relationships in a detectable way. 
	- As a result, manipulation detection feature extractors must learn the relationship between a pixel and its local neighborhood while simultaneously suppressing the content of the image so that content dependent features are not learned. 
	- For this to occur, the first convolutional layer must not be allowed freely evolve into any set of filters. 
	- Instead, it must be constrained to evolve filters with the desired properties described above
- To accomplish this, we propose creating the first layer of our CNN using convolutional filters that are constrained to learn only a set of prediction error filters. 
	- Prediction error filters are filters that predict the pixel value at the center of the filter window, then subtract this central value to produce the prediction error. 
	- More explicitly, each of the $K$ filters $w^(1)_k$ in the first layer of the CNN have the following constraints placed on them:
	  $$\begin{cases} w^{(1)}_k (0, 0) &= -1 \\
	   \sum_{\ell,m\neq0} w^{(1)}_k (\ell, m) &= 1
	   \end{cases}\tag{4}$$
	   where 
	   -  $w ^{(1)}_k (\ell, m)$ is the filter weight at the $(\ell, m)$ position 
	   - $w^{(1)}_k (0, 0)$ is the filter weight at the center of the filter window.
   - ![[Pasted image 20230929110554.png|350]]
- The network architecture 
![[Pasted image 20230929112136.png|Figure 2: An illustration of the proposed CNN Architecture. The network’s input dimension is 51529 neurons and the remaining 8 layers have 596748, 802816, 200704, 150528, 37632, 4096, 4096 and 5 neurons respectively]]

**remarks**
- 
**references to detection methods**
- [20] Over the past several years, researchers have developed a variety of information forensic techniques to determine the authenticity and processing history of digital images
- Recent experimental evidence has shown that tools initially developed to perform steganalysis are capable of detecting a wide variety of image editing operations [18]
- Another recent effort towards developing universal forensic detectors operates by building Gaussian mixture models (GMMs) of image patches in unaltered and manipulated images [3].
- This effect has recently been observed by Chen et al. during their efforts train a CNN to perform median filtering detection [2]
# PDF 