#JointCNN #DetectionModel #Differential
Title: 

# Summary 

Proposed novel approaches to improve generalization performance: 
- domain adaption, cite 14 
- semantic hidden information through generative models, cite no. 12 and 13
- and anomaly detection cite no. 10,17 and 18

Proposed identity-aware detection methods:
- cite 19, improvement by including itenty awarness was shown
- cite 16, learns information specific to the identity of a subject.
- In this contect, differential detection algorithms are a type of identity-aware technique where both a trusted and a suspected image are fed into the algorithm. 


Proposal: 
- a differential approach for anomaly detection is proposed
  1. first , feature embeddings are obtained from a suspected and a trusted image
  2. Then, the extracted information is fused. 
  3. The fused information is given as input to a one-class classifier.
- the anomaly detection module is trained on BPs only, in order to learn the natural changes (intra class variation).

Existing software detection schemes use 
1. texture analysis
2. digital forensics
3. deep-learning techniques

Models used for extraction of deep face embeddings are existing pre-trained state-of-the-art Face Recognition models.
- a pre-trained model of ArcFace based on the ResNet100

Faces are aligned using 
- RetinaFace

Four one class classifiers are used 
- Gaussian Mixture Model (GMM)
- Support Vector Machines (SVM)
- Variational Autoencoder (VAE)
- Single-Objective Generative Adversarial Active Learning (SO-GAAL)

THree Fusion Schemes are used 
- SUB
- SUB^2
- ABS
Given two deep face embeddings
- A (from reference image)
- B (from the probe image)
$$
\begin{align}
SUB &= A-B\\
SUB^2&= (A-B)^2\\
ABS &= |A-B|
\end{align}
$$

Datasets 
1. Bona Fide Presentations
   - academic version of the [[UNCW MORPH]]
   - [[CASIA-FaceV5]]
   - [[FERET]]
   - [[FRGCv2]]
   - [[XCSMAD]]
   - [[CSMAD-Mobile]]
   - [[HDA_MPA_DB]]
2. Digital manipulations
   - [[FERET]]
   - [[FRGCv2]]
3. Attack Presentations
   - [[XCSMAD]]
   - [[CSMAD-Mobile]]
   - [[HDA_MPA_DB]]

Manipulation Tools used 
1. Retouching
   - InstaBeauty
   - Fotorus
2. morphing
   - FaceFusion
   - UBO Morpher
3. face swapping
   - fewshot-face
   - simple_faceswap




# PDF Article
![[MI Differential_Anomaly_Detection_for_Facial_Images.pdf]]