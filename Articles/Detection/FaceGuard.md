#JointCNN #DetectionModel
#Pub2023 
# Title
FaceGuard: A Self-Supervised Defense Against Adversarial Face Images

# Summary

Focus
- defending against obfuscation attacks 

The 2 requirements for an adversarial generator, given an input probe image $\mathbf{x}$
1. synthesize an adversarial face image $\mathbf{x}_{adv} = \mathbf{x} + \delta$ such that SOTA AFR  systems fail to match $\mathbf{x}_{adv}$ and $\mathbf{x}$
2. limit the magnitude of perturbations $\|\delta\|_p$ such that $\mathbf{x}_{adv}$ appears very similar to $\mathbf{x}$ to humans.

Adversarial face perturbation methods 
- gradient-based attacks 
  - FGSM [34]
  - PGD [34]
  - here every single pixel in the face image is perturbed
- other method
  - AdvFaces [13]
  - SemanticAdv [40]
  - only salient facial regions are perturbed those are eyes, nose, and mouth 
- other 2 method
  - GFLM [10]
  - performs geometric warping to the face. 

FaceGuard's relevant parts 
- integration of three things in one unified framework 
  1. adversarial face generator
	- a stochastic generator that outputs diverse perturbations -- adds robustness 
  2. a detector
	- continuously learns to distinguish the above perturbed images from real faces
  3. a purifier
	  - removes the adversarial perturbations from the synthesized image

Six unseen Adversarial attacks that have high success rates evading ArcFace [14]
1. FGSM [19]
2. PGD [34]
3. DeepFool [37]
4. AdvFaces [13]
5. GFLM [10]
6. Semantic Adv [40]
Face guard is evaluated on those six attacks

It has previously been shown that adversarial training can significantly reduce classification accuracy on real examples. 
- this means that by including adversarial faces in the training of FR systems the detection of faces also real ones can  significantly reduce accuracy. 

Datasets used 
- [[CASIA-WebFace]]
- [[LFW]]
- [[CelebA]]
- [[FFHQ]]

Future work
-  whether an attention mechanism can further improve adversarial purification 

# References 
- [[FFD]]


# PDF Article 
![[FaceGuard_A_Self-Supervised_Defense_Against_Adversarial_Face_Images.pdf]]


# More