A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
#A
### Ablation study
In general, an ablation study is a set of experiments in which components of a machine learning system are removed/replaced in order to measure the impact of these components on the performance of the system.

# B
### Bi-class classifiers
these classifiers are trained on both *bona fide presentations* (BPs) and attack presentations
#I
### IINC 

$IINC= \frac{1}{3-|\mathbf{U}|}\cdot 
\begin{cases}
0 &,\text{if } \overline{\mathbf{M}_\text{gt}} = 0 \text{ and } \overline{\mathbf{M}_\text{att}} = 0\\
1 &,\text{if } \overline{\mathbf{M}_\text{gt}} = 0 \text{ xor }\, \overline{\mathbf{M}_\text{att}} = 0\\
\left(2- \frac{|\mathbf{I}|}{| \mathbf{M}_\text{att}|} - \frac{|\mathbf{I}|}{|\mathbf{M}_\text{gt}|}\right)&, \text{ otherwise}
\end{cases}$
where $\mathbf{I}$ and $\mathbf{U}$ are the intersection and union between the ground truth map, $\mathbf{M}_\text{gt}$, and the predicted map, $\mathbf{M}_\text{att}$, respectively. 
$\overline{\mathbf{M}}$ and $|\mathbf{M}|$ are the mean and the $L_1$ norm of $\mathbf{M}$, respectively. 
The two fractional terms measure the ratio of the area of the intersection w.r.t. the area of each map, respectively. 
# M
### Morphing attack 
*A morphing attack is a face image which is purposefully manipulated to be matched with the probe images of more than one identity*  \[[[SPL-MAD]]\]


# O 
### One-class classifiers
these classifiers are only trained on *bona fide presentations*, an image is then evaluated based on whether it is an anomaly or not. 
Examples are 
- Gaussian Mixture Model (GMM)
- Support Vector Machines (SVM)
- Variational Autoencoder (VAE)
- Single-Objective Generative Adversarial Active Learning (SO-GAAL)

# P 
### Presentation attack
Presentation attack refers to an attack using an instrument with the intention to affect the normal operation of the biometric system 
These attacks are in the physical domain, as they do not use software to manipulate an image. 

### Purification
A pre-processing strategy, that involves automatically removing adversarial perturbations in the input image prior to passing them to a face matcher.
