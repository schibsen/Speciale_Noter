Title: Median Filtering Forensics Based on Convolutional Neural Networks
# Info

**Publication**:
- 2015
**differential**:
- NO
**no-reference**:
- YES
**Datasets**:
- 15352 images 
- BOSSbase 1.01 [20]
- UCID database [21]
- BOSS RAW database [22]
- Dresden Image Database [23]
- NRCS Photo Gallery database [24]
- Each of the 4 databases contributes 1338 images, and BOSSbase database contributes 10000 images.
- All images are converted to gray-scale images before any further processing
- Each image from the original composite database belongs to the negative class and its median filtered version belongs to the positive class. 
- The training set contains half number of images in each class, while the other half of images compose the testing set.
**performance**:
- Detection accuracy: 
  $$A_c = \frac{c}{n}$$
- where is the number of correctly predicted samples and is the number of total testing images
![[Pasted image 20230928121025.png|500]]
**attacks**:
- digital: using median filters for smoothing
**Motivation(if relevant)**
- Current image median filtering forensics algorithms mainly extract features manually.
- To deal with the challenge of detecting median filtering from small-size and compressed image blocks
- Existing median filtering forensics techniques mainly depend on manually selected features, and the feature extraction and the classification are generally separated and not optimized simultaneously in an iterative way
**Proposal(brief)**:
- To address this concern, in this paper, instead of constructing better artificial features, we plan to automatically learn feature representations jointly with the classification for median filtering forensics.
- a median filtering detection method based on convolutional neural networks (CNNs), which can automatically learn and obtain features directly from the image.
- Unlike conventional CNN models, the first layer of our CNN framework is a filter layer that accepts an image as the input and outputs its median filtering residual (MFR).
- Then, via alternating convolutional layers and pooling layers to learn hierarchical representations, we obtain multiple features for further classification
![[Pasted image 20230928115356.png]]
**Method(long)**:
- median filtering has the properties of nonlinearity and preserving edge information of an image
- 
**remarks**
- 
**references to detection methods**
- 
# PDF 
![[Median_Filtering_Forensics_Based_on_Convolutional_Neural_Networks.pdf]]