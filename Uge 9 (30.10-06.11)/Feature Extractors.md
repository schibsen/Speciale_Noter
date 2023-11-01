https://deci.ai/blog/sota-dnns-overview/
# Introduction 

>[!INFO] Feature Extractor 
> A **feature extractor** is a component of a machine learning model that is responsible for preparing input features for the model. It is used to transform raw data into a format that can be used by machine learning algorithms. [The feature extractor is typically used to extract relevant information from the input data and convert it into a set of features that can be used to train the model](https://huggingface.co/docs/transformers/main_classes/feature_extractor)

In the context of face images, feature extractors are used to extract relevant information from the image that can be used to identify or classify faces. Some of the most common features extracted from face images include:

- [**Eigenfaces**: A set of eigenvectors that are used to represent the variation in face images](https://ieeexplore.ieee.org/document/8225635/)[3](https://ieeexplore.ieee.org/document/8225635/).
- [**Local Binary Patterns (LBP)**: A texture descriptor that is used to describe local patterns in an image](https://arxiv.org/pdf/1708.02721)[4](https://arxiv.org/pdf/1708.02721).
- [**Histogram of Oriented Gradients (HOG)**: A feature descriptor that is used to describe the distribution of gradients in an image](https://arxiv.org/pdf/1708.02721)[4](https://arxiv.org/pdf/1708.02721).
- **Deep Convolutional Neural Networks (CNNs)**: A type of neural network that is commonly used for image recognition tasks, including face recognition.

[There are several open-source libraries available for face recognition that provide pre-trained feature extractors, including InsightFace, Deepface, and Face Recognition](https://github.com/topics/face-extractor)[5](https://github.com/topics/face-extractor). These libraries can be used to extract features from face images and use them to train machine learning models.

# Face Recognition methods i want to use 
https://paperswithcode.com/task/face-recognition
- GhostFaceNetV2-1
- Fine tuned ArcFace
- 

# SOTA Feature extractors 
- VGG-Oxford [21],                                           
- AFFFE [22], 
- ArcFaceInsightFace 4 [23], 
- FaceNet5 [24], 
- IncResNetVI-MSCeleblMCenterLoss 6 [25], 
- ResNet50-VGG2-ArcFace 8 [26],
- and MobileNetV2- MSCeleb1M-ArcFace 9
- DeepFace
- ArcFace
- VGGFace
- VGGFace 2
- DeepID


[21] 0, M, Parkhi, A, Vedaldi, and A, Zisserman, "Deep face recognition," 2015, 
[22] eLi, M, Gunther, and T. E, Boult, "Eclipse: Ensembles of centroids leveraging iteratively processed spatial eclipse clustering," in 2018 IEEE Winter Conference on Applications ofComputer Vision (WACV), IEEE, 2018, pp, 131-140, 
[23] J, Deng, J, Guo, X, Niannan, and S, Zafeiriou, "Arcface: Additive angular margin loss for deep face recognition," in Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2019, 
[24] F, Schroff, D, Kalenichenko, and J, Philbin, "Facenet: A unified embedding for face recognition and clustering," in Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2015, pp, 815-823, 
[25] T. de Freitas Pereira, A, Anjos, and S, Marcel, "Heterogeneous face recognition using domain specific units," IEEE Transactions on Information Forensics and Security, vol, 14, no, 7, pp, 1803-1816, 2018, 
[26] T. de Freitas Pereira and S, Marcel, "Fairness in biometrics: a figure of merit to assess biometric verification systems," arXiv e-prints, pp, arXiv2011, 2020, [Online], Available: https:llarxiv,org/abs/201L02395v2

#### Table 
| Model                           | Pub Year |
| :----------------               | :------: |
| VGGFace                         |   ??     | 
| VGGFace 2                       |   ??     | 
| ArcFace                         |  2019    | 
| DeepFace                        |  2014    |
| DeepID                          |  2014    |
| VGG-Oxford                      |  2015    |
| AFFFE                           |  2018    |
| ArcFace InsightFace             |  2019    |
| IncResNetVI-MSCeleblMCenterLoss |  2015    |
| ResNet50-VGG2-ArcFace           |  2018    |
| MobileNetV2- MSCeleb1M-ArcFace  |  2020    |



