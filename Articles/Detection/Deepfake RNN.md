Title: Deepfake Video Detection Using Recurrent Neural Networks

NOT RELEVANT AT THE MOMENT SINCE RELATED TO VIDEOS 
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
- 
**Proposal(brief)**:
- This paper proposes a temporal-aware pipeline to automatically detect deepfake videos.
- Our system uses a convolutional neural network (CNN) to extract frame-level features.
- These features are then used to train a recurrent neural network (RNN) that learns to classify if a video has been subject to manipulation or not.
- we propose a two-stage analysis composed of a CNN to extract features at the frame level followed by a temporally-aware RNN network to capture temporal inconsistencies between frames introduced by the face-swapping process.
**Method(long)**:
- 
**remarks**
- 
**references to detection methods**
- Both featurebased [35, 16] and CNN-based [18, 19] integrity analysis methods have been explored in the literature.
- Techniques that detect face-based manipulations include methods that distinguish computer generated faces from natural ones such as Conotter et al. [13] or Rahmouni et al. [33]. 
- In biometry, Raghavendra et al. [32] recently proposed to detect morphed faces with two pretrained deep CNNs and Zhou et al. [41] proposed detection of two different face swapping manipulations using a two-stream network.
**good citations for thesis**
- Recent advances [21, 42] have radically changed the playing field of image and video manipulation. The democratization of modern tools such as Tensorflow [6] or Keras [12] coupled with the open accessibility of the recent technical literature and cheap access to compute infrastructure have propelled this paradigm shift
- Convolutional autoencoders [38, 37] and generative adversarial network (GAN) [17, 7] models have made tampering images and videos, which used to be reserved to highly-trained professionals, a broadly accessible operation within reach of almost any individual with a computer. Smartphone and desktop applications like FaceApp [1] and FakeApp [2] are built upon this progress.
- As presented in the Malicious AI report [11], researchers in artificial intelligence should always reflect on the dualuse nature of their work, allowing misuse considerations to influence research priorities and norms.
# PDF 