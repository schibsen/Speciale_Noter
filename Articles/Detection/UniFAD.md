# Title
Unified Detection of Digital and Physical face Attacks

#Pub2023 #DetectionModel  #MLT #Differential 

#AdversarialManipulation #DigitalManipulation #Spoofs

#GrandFake

# Referencer 
[[Mathias Article]]
[[FaceGuard]]
[[FFD]]
[[SSRFCN]]
[[One-Class]]



# Summary

Proposal:
- a new unified attack detection framework that
  1. first utilizes k-means to partition the 25 attack types
  2. then learns shared and attack specific representations to distinguish them from bona fides. 

Dataset used 
- GrandFake

Drawback of JointCNN
- learning a common festure space to discriminate all attack types from bona fides is challenging 
- may fail to generalize well even on attack types seen during training.
- shown by training a JointCNN on the 25 attack types

Unifying multiple JointCNNs
- defining categories manually, i.e Adversarial, Digital and Physical 
- train a JointCNN for each of the attacks 
- performs better than single JointCNN
- but it is seen that Gan manipulations under Digital are closer related to Adversarial than other digital manipulations
- thus categories should not be manual defined. 

Adversarial attacks
- [[FGSM]]
- [[PGD]]
- [[DeepFool]]
- [[AdvFaces]]
- [[GFLM]]
- [[SemanticAdv]]

Digital Manipulation
- More 

Physical Spoofs
- More


Conclusion 
??

# PDF article 
![[Unified_Detection_of_Digital_and_Physical_Face_Attacks.pdf]]

# More 