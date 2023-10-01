Title: MesoNet: a Compact Facial Video Forgery Detection Network
# Info

**Publication**:
- 2018
**differential**:
- NO, since its videos
**no-reference**:
- Yes, since its videos
**Datasets**:
- create own 
- 175 rushes of forged videos have been collected from different platforms. Their duration ranges from two seconds to three minutes and have a minimum resolution of 854 × 480 pixels. All videos are compressed using the H.264 codec but with different compression levels, which puts us in real conditions of analysis.
- All the faces have been extracted using the Viola-Jones detector [27] and aligned using a trained neural network for facial landmark detection [12].
- FaceForensics dataset [20] [[FaceForensics]]
**performance**:
- the two models: results for the Deepfake dataset
![[Pasted image 20230929155317.png|Table 3. Classification scores of several networks on the Deepfake dataset, considering each frame independently.]]
- the two models on the Face2Face dataset
![[Pasted image 20230929155633.png|Table 4. Classification scores of several networks on the FaceForensics dataset, considering each frame independently.]]
![[Pasted image 20230929155712.png|Figure 6. ROC curves of the evaluated classifiers on the Deepfake dataset (a) and the Face2Face dataset compressed at rate 23 (b).]]
- aggregation results
![[Pasted image 20230929155915.png|Table 5. Video classification scores on the two dataset using image aggregation, with the Face2Face dataset compressed at rate 23.]]
**attacks**:
- Digital:  two recent techniques used to generate hyper-realistic forged videos: Deepfake and Face2Face
**Motivation(if relevant)**
- Traditional image forensics techniques are usually not well suited to videos due to the compression that strongly degrades the data.
- For the last years, deep learning methods has been successfully employed for digital image forensics. Amongst others, Barni et al. [2] use deep learning to locally detect double JPEG compression on images. Rao and Ni [18] propose a network to detect image splicing. Bayar and Stamm [3] target any image general falsification. Rahmouni et al. [17] distinguish computer graphics from photographic images.
- Up to our knowledge, there is no other method dedicated to the detection of the Deepfake video falsification technique
**Proposal(brief)**:
- This paper follows a deep learning approach and presents two networks, both with a low number of layers to focus on the mesoscopic properties of images
**Method(long)**:
- meso 4
![[Pasted image 20230929152255.png|Figure 4. The network architecture of Meso-4. Layers and parameters are displayed in the boxes, output sizes next to the arrows.]]
- MesoInception -4: An alternative structure consists in replacing the first two convolutional layers of Meso4 by a variant of the inception module introduced by Szegedy et al [25].
![[Pasted image 20230929152440.png|Figure 5. Architecture of the inception modules used in MesoInception-4. The module is parameterized using a, b, c, d ∈ N. The dilated convolutions are computed without stride.]]

**remarks**
- 
**references to detection methods**
- For the last years, deep learning methods has been successfully employed for digital image forensics. 
	- Amongst others, Barni et al. [2] use deep learning to locally detect double JPEG compression on images. 
	- Rao and Ni [18] propose a network to detect image splicing. 
	- Bayar and Stamm [3] target any image general falsification.
	- Rahmouni et al. [17] distinguish computer graphics from photographic images.
# PDF 