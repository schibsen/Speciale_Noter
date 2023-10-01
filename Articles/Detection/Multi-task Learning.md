Title: Multi-task Learning For Detecting and Segmenting Manipulated Facial Images and Videos
# Info

**Publication**:
- 
**differential**:
- 
**no-reference**:
- 
**Datasets**:
- 
**performance**:
- 
**attacks**:
- 
**Motivation(if relevant)**
- Most existing forensic segmentation methods focus on three commonly used means of tampering: removal, copy-move, and splicing [6, 32, 7].
**Proposal(brief)**:
- We have designed a convolutional neural network that uses the multi-task learning approach to simultaneously detect manipulated images and videos and locate the manipulated regions for each query.
- Information gained by performing one task is shared with the other task and thereby enhance the performance of both tasks. A semi-supervised learning approach is used to improve the network’s generalizability.
- The network includes an encoder and a Y-shaped decoder. 
- Activation of the encoded features is used for the binary classification. 
- The output of one branch of the decoder is used for segmenting the manipulated regions while that of the other branch is used for reconstructing the input, which helps improve overall performance.
- Our autoencoder comprises an encoder and a Y-shaped decoder and is trained in a semisupervised manner
**Method(long)**:
- There are two commonly used approaches to locating manipulated regions in images: segmenting the entire input image and repeatedly performing binary classification using a sliding window. 
![[Pasted image 20231001215410.png|Figure 2. Overview of proposed network.]]

![[Pasted image 20231001215503.png|Figure 3. Proposed autoencoder with Y-shaped decoder for detecting and segmenting manipulated facial images.]]
**remarks**
- 
**references to detection methods**
- Cozzolino et al. addressed the transferability problem of several state-of-the-art spoofing detectors [11] and developed an autoencoder-like architecture that supports generalization and can be easily adapted to a new domain with simple fine-tuning.
# PDF 