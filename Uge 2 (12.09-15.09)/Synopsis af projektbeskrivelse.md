
# Background on Facial recognition
- where is it used
- why is it used ? i.e. non.inasive compaed to other biometric systems

# Motivation for MAD 
- with growing use of AFR systems comes greater interest in fooling these
- methods get more advanced with the improvements in the AI world
- counte research is needed
### Relevant sources 
- [3,4] [[One-Class]]
# Motivation for generalization 
- well working MAD exist for specific attacks or specific domains, however trouble of generalizing well to unseen attacks and to other domains

### physical 
 Network Efficiency A majority of prior work on CNN-based face anti-spoofing employs architectures that are densely connected with thir- teen convolutional layers [1, 20, 51, 52, 54]. Even with the placement of skip connections, the number of learnable parameters exceed 2.7M . As we see in Table I, only a limited amount of training data4 is generally available in face anti-spoofing datasets. Limited data coupled with the large number of trainable parameters causes current approaches to overfit, leading to poor generalization performance under unknown attack scenarios [[SSRFCN]]
### Relevant sources 
- [14] [[One-Class]]

# Related work 
[[Articles and domain flowchart]]
# Related work in the Single domains 
## Physical 
PAD 2D attacks 
- [5-9] [[One-Class]]

CNN based methods perform better than feature-based, recently 
- [[19,10,20,21] [[One-Class]]

Binary classification
- most of the methods handle the PAD problem as a binary classification problem.
- which overfit to the known attacks resulting in poor generalization to unseen attacks.

One-Class classifiers (OCCs)
- OCC provides a straightforward way of handling the unseen attack scenario by modelling the distribution of the bona fide class alone !
- Arashloo et al [22] and Nikisins eta al [23] [[One-Class]] have shown the effectiveness of one class methods against unseen attacks
    - the performance in known attack protocols was inferior to that of binary classifier, but better for unseen attacks.
- Xiong et al [24][[One-Class]] used auto-encoders and ine-class classifiers with texture feature extraction, performed worse than CNN methods.
- 


## Digital 
## Adversarial 

# Related work in combinations of pairs 
## Physical and Digital 
- what my original goal was to focus on 
## Digital and adversarial 

# Related work all three 
- argue that adversarial and the two other domains are tofar apart to make a unified framework, instead one would need an ensemble method for this. as has been doen in [[SPL-MAD]]
- 
