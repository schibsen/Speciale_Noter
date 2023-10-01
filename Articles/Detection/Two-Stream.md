Title: Two-Stream Neural Networks for Tampered Face Detection

#Pub2018
#JointCNN 
# Info 
**Publication**: 
- 2018
**differential**: 
- YES, ish we do use other random selected images as reference for the second stream, as posiitves, i.e. Figure 4
**no-reference**:
- NO
**Datasets**:
- we created a dataset utilizing one iOS app called SwapMe [2] and an open-source face swap application called FaceSwap [1].
- post processing such as boundary blurring, resizing and blending is applied to the tampered face
- we have 705 tampered faces and 1400 authentic faces for training, and 900 authentic faces and 300 tampered faces for testing.
- no information on which dataset applications where used on 
**performance** 
- ROC and AUC 
- AUC: 0.927

| Methods | AUC | 
| ---------- | --------- |
| IDC                         | 0.543 |
| CFA Pattern                 | 0.618 |
| Steganalysis features + SVM | 0.794 |
| Face classification stream  | 0.854 |
| Patch triplet stream        | 0.875 |
| Two-stream network (Ours)   | **0.927** |
![[Pasted image 20230928110049.png|200]]
**attacks**: 
- digital manipulations: image splicing, FaceSwap swapFace, i.e ID swap or FaceSwap
- image splicing: the process of cutting one part of a source image, such as the face regions, and inserting it in the target image
**Proposal**: 
- a two-stream network for face tampering detection
- to capture both tampering artifact evidence and local noise residual evidence
![[Two-Stream-Architecture.png|600]]
><small>Figure 2. Illustration of our two-stream network. The face classification stream models visual appearance by classifying a face is tampered or not. The patch triplet stream is trained on steganalysis features to ensure patches from the same image are close in the embedding space, and an SVM trained on the learned features classifies each patch. Finally, the scores of two streams are fused to recognize a tampered face.</small>

**method**: 
- train GoogleLeNet to detect tampering artifacts in a face classification stream
- train a patch based triplet network to leverage features capturing local noise residuals and camera characteristics as a second stream
- **Stream one**: CNN based face classification stream, based on GoogLeNet, 
	- classify whether a face is tampered or not, 
	- thus it learns the aftrifacts created by the tampering process
	- GoogLeNet Inception V3 model
- **Stream Two**: steganalysis based triplet stream: based on patch level steganalysis features, captures lowlevel camera characteristics like CFA pattern and local noise residuals.
	- trained on steganalysis features of image patches with atriplet loss
	- models the traces left by incamera processing and local noice characteristics
	- By training this triplet network, we ensure that a pair of patches from the same image are closer in the learned embedding space, while the distance between a pair of patches from two different images is large
	- We model the embedding, f, by a two layer fully connected neural network
- **Triplet network i.e. stream two**:
	- The triplet network is designed to determine whether or not two patches come from the same image. Face tampering detection works in a similar way. 
	- All the patches in an authentic region are from the same image and have small distances between each other in triplet embedding space, while the patches in tampered face regions have large distance from those authentic patches in the triplet embedding space because they are from another image.
	- For each tampered image, the tampered regions have different characteristics from the authentic regions.
	- Therefore, we treat the tampered and authentic regions in each image as two different classes and train a classifier for each image to predict the tampered regions.
	- We choose SVM as our classifier and train it for each test face on-thefly
	- The SVM samples are obtained by extracting the triplet features on each patch through sliding windows
	- we apply the trained SVM on face patches, and the average score of face patches is used as the face-level score.
	- relevant picture below
![[Pasted image 20230928101640.png|600]]
><small>Figure 4. Demonstration of SVM training process. Suppose we want to test on the left face in the test image in a sliding window fashion. Green boxes are the test face patches; red boxes are randomly selected patches from other images and used as positive samples; blue boxes are the negative samples indicating patches from the same image. After SVM prediction, green boxes are more likely to be the ones from other images and thus the left face in the test image is classified to be a tampered face.</small>

- Instead of utilizing steganalysis features directly, we train a triplet network after extracting steganalysis features to allow the model to refine steganalysis features.
- Combining the two streams reveals both evidence of highlevel tampering artifacts and low-level noise residual features, and yields very good performance for face tamper detection.

**remarks**
- they rely on camera intrinsic information ?? 

**references to detection methods **
- [20, 14, 4, 11]
- local noise analysis: fails to deal with tampered images constructed using careful post processing
- Color Filter Array (CFA) models: cannot deal with resized images.
- CNNs learn tampering evidence [3, 21, 7] **First that use CNN and not standard computer vision**
	- by adding an additional median filter layer before the first convolutional layer, Chen et al. [7] achieved good performance in median filtering tampering.
	- Bayar et al. [3] designed an adaptive filter kernel layer to estimate the filter kernel used in the tampering process, detecting various filtering tampered contents. However, the performance degrades significantly when multiple post processing techniques are applied to tampered regions. 
	- Rao et al. [21] combined a CNN with steganalysis features by initializing the kernel of the first convolution layer with steganalysis filter kernels
- an rich models [15, 9, 10, 16], which are models of the noise components that produce informative features for steganalysis

# PDF
![[Two-Stream Neural Networks for Tampered Face Detection.pdf]]