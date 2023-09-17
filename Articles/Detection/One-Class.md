
#JointCNN #DetectionModel  #OpenSourceCode # OpenSourceProtocols
#Pub2020 
# Title
Title: Learning One Class Representations for Face Presentation Attack Detection using Multi-channel Convolutional Neural Networks

Code and protocols: https://gitlab.idiap.ch/bob/bob.paper.oneclass_mccnn_2019
# Summary 
Proposal: 
- a one-class classifier based framework
- the feature representation is learned with a CNN to have discriminative properties. 
- the core is a multi-channel CNN trained to learn the embedding using a specific loss function. 

Aim: 
- to learn a compact representation for the bona fide class while leveraging the discriminative information for PAD task. 

Main Contributions: 
- a novel multi-channel one-class classifier-based approach is proposed for unseen attack detection
- a novel loss function is proposed which learns a compact and discriminative representation of the face for PAD task, leveraging the information provided from known attacks. 


Proposed method 
- in practice the performance of one class classifiers are inferior compared to binary classifiers for known attacks, since they do not leverage useful information from the known attacks. 
- there is a necessity of a method which can learn a compact one class representation while utilizing the discriminative information from known attacks. 
- a CNN based approach to learn feature representation 
- novel loss function to learn as representation of bonafide samples leveraging the known attack classes. 

Components of the proposed framework 
1. preprocessing
   - face detection MTCNN algorithm [42]
   - face landmark detection Supervised Descent Method (SDM) [43]
   - alignment 
   - convertion to grayscale with resolution 128x128
   - normalization using Mean Absolute Deviation (MAD)[44]
2. Network architecture and training
   - multi-channel PAD framework: "Multi-channel Convolutional Neural Network" (MCCNN)[14] as our base network 
   - MCNN is trained with BCE and OCCL
   - the trained weights of the network are frozen afterwards. 
3. One-class Gaussian Mixture Model
   - the frozen weights are now used as a fixed feature extractor for the PAD taks. 
   - objective is to learn a One-Class classifier using the features obtained 
   - The one class GMM is a generative approach
   - EM is used to compute the parameters of the GMM
   - the important difference to a one-class classifier based framework for PAD is that the features used in the classifier are learned !! 

Datasets testing 
- [[WMCA]] [14]: https://www.idiap.ch/dataset/wmca
- [[MLFP]] [35]
- [[SiW-M]] [28]

Metrics 
- APCER
- BPCER
- ACER
- ROC curves
- EER
- 

# PDF Article
![[OneClass Learning one class representations for face presentation attack detection using multi-channel convolutional neural networks.pdf]]
