# MAD 
Differential MAD can be divided into two categories. 

**The first category** 
- are algorithms that *compare feature vectors extracted from extracted from trusted live captures and potential morphs*.
- Single image algorithms can be extended to differential algorithms, e.g., by estimating differences between feature vectors [7]. 
- The additional information of the trusted live capture might improve the performance and robustness of the detection algorithm. 
- Further, algorithms explicitly utilizing this additional information have been introduced in [9], [11], where the distances between features of facial landmarks are estimated. 

**The second category**
- contains algorithms that try to *reverse the process of morphing*.
- Here the assumption is that if two subjects are represented in the morphed image and the trusted live capture is subtracted from the possibly morphed reference, in the case of a morphed face image the identity of the second subject becomes more dominant, leading to a lower face recognition scores. 
- If there is no other subject in the image, only the existing one remains. 
- In [13], [14] the so-called demorphing algorithm was proposed, an approach where reversion is done explicitly.
- In addition to the explicit demorphing approach, demorphing based on a Generative Adversarial Network (GAN) is proposed in [16].