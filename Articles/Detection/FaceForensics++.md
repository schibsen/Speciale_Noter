Title: FaceForensics++: Learning to Detect Manipulated Facial Images
# Info

**Publication**:
- 2019
**differential**:
- NO
**no-reference**:
- YES, per-frame binary classification
**Datasets**:
- create own
- Referenced: The National Institute of Standards and Technology (NIST) released the most extensive dataset for generic image manipulation comprising about 50, 000 forged images (both local and global manipulations) and around 500 forged videos [32].
- 
**performance**:
![[Pasted image 20231001212757.png|Figure 6: Binary detection accuracy of all evaluated architectures on the different manipulation methods using face tracking when trained on our different manipulation methods separately.]]
![[Pasted image 20231001212714.png|Figure 7: Binary precision values of our baselines when trained on all four manipulation methods simulatenously. See Table 1 for the average accuracy values. Aside from the Full Image XceptionNet, we use the proposed preextraction of the face region as input to the approaches.]]
![[Pasted image 20231001212840.png|Table 1: Binary detection accuracy of our baselines when trained on all four manipulation methods. Besides the na¨ıve full image XceptionNet, all methods are trained on a conservative crop (enlarged by a factor of 1.3) around the center of the tracked face.]]
![[Pasted image 20231001213014.png|Figure 8: The detection performance of our approach using XceptionNet depends on the training corpus size. Especially, for low quality video data, a large database is needed.]]
![[Pasted image 20231001213327.png|Table 2: Results of the low quality trained model of each detection method on our benchmark. We report precision results for DeepFakes (DF), Face2Face (F2F), FaceSwap (FS), NeuralTextures (NT), and pristine images (Real) as well as the overall total accuracy.]]
**attacks**:
- Digital: FaceSwap, DeepFake, Face2Face, NeuralTextures
**Motivation(if relevant)**
- 
**Proposal(brief)**:
- . We leverage recent advances in deep learning, in particular, the ability to learn extremely powerful image features with convolutional neural networks (CNNs). 
- We tackle the detection problem by training a neural network in a supervised fashion.
- we propose an automated benchmark that considers the four manipulation methods in a realistic scenario, i.e., with random compression and random dimensions.
- Using this benchmark, we evaluate the current state-of-the-art detection methods as well as our forgery detection pipeline that considers the restricted field of facial manipulation methods.
![[Pasted image 20231001212145.png|Figure 5: Our domain-specific forgery detection pipeline for facial manipulations: the input image is processed by a robust face tracking method; we use the information to extract the region of the image covered by the face; this region is fed into a learned classification network that outputs the prediction.]]

**Method(long)**:
- 
**remarks**
- improvement by adding a conservative crop, might be compared to attention mechanism 
**references to detection methods**
- A comprehensive state-of-the-art report has been published by Zollhofer ¨ et al. [68].
- Recently, several face image synthesis approaches using deep learning techniques have been proposed. Lu et al. [47] provide an overview.
- More recent literature concentrates on CNN-based solutions, through both supervised and unsupervised learning [10, 17, 12, 9, 35, 67].
- Several other works explicitly refer to detecting manipulations related to faces, such as distinguishing computer generated faces from natural ones [22, 15, 51],
- morphed faces [50],
- face splicing [24, 23],exploit specific artifacts arising from the synthesis process in this case color, texture and shape cues [24, 23]. 
- face swapping [66, 38]
- and DeepFakes [5, 44, 33].
- For face manipulation detection, some approaches exploit specific artifacts arising from the synthesis process, such as eye blinking [44],
- other works propose a deep network trained to capture the subtle inconsistencies arising from low-level and/or high level features [50, 66, 38, 5, 33].

# PDF 
![[FaceForensics++- Learning to Detect Manipulated Facial Images.pdf]]