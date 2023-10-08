#Pub2020 

Title: Deep Face Representations for Differential Morphing Attack Detection

# Info

**Publication**:
- 2020
**Classification**
- seems to be One-Class / anomaly but not sure !! 
**differential**:
- YES
**no-reference**:
- NO 
**Datasets**:
- In this work, subsets of the FERET and FRGCv2 face databases are used to create a realistic database for training and testing of MAD algorithms, containing a large number of ICAO-compliant bona fide facial images, corresponding unconstrained probe images, and morphed images created with four different face morphing tools.
- Furthermore, multiple post-processings are applied on the reference images, e.g., print-scan and JPEG2000 compression.
**performance**:
- 
**attacks**:
- digital: morphing
**Motivation(if relevant)**
- The vulnerability of facial recognition systems to face morphing attacks is well known. 
	- Many different approaches for morphing attack detection (MAD) have been proposed in the scientific literature. 
	- However, the MAD algorithms proposed so far have mostly been trained and tested on datasets whose distributions of image characteristics are either very limited (e.g., only created with a single morphing tool) or rather unrealistic (e.g., no print-scan transformation). 
	- As a consequence, these methods easily overfit on certain image types and the results presented cannot be expected to apply to real-world scenarios.
- In many countries, the facial image submitted for an electronic travel document is provided by the applicant either in analogue (i.e., print on paper) or digital form. 
	- Therefore, an attacker (e.g., a wanted criminal or a foreigner without authorization to enter a territory) could morph his face image with the face image of a similar looking accomplice who could apply for a passport or another electronic travel document with the morphed image.
	- the attacker can then use the electronic travel document issued to the accomplice to pass through automatic or manual border controls.
- While many publications report impressive detection rates, these results are hardly applicable to real-world scenarios. 
	1. Firstly, the datasets used for evaluation are not realistic. 
	   - In particular, most publications ( [18]–[20] and [21] being exceptions) do not consider variations in post-processings of the images, e.g., print-scan transformation or severe compression, which can occur in real-world scenarios and may drastically reduce detectable artefacts from the morphing process.
	   - In addition, the vast majority of previous publications on differential MAD (with the notable exception of [14]) use probe images that do not exhibit a realistic intra-subject variance, e.g., facial pose and expression, illumination, the subject’s appearance (glasses, beard, hair style, clothing, cosmetics) and aging. 
	2. Secondly, the datasets used for training and evaluation are not sufficiently distinct but contain images with similar characteristics. 
	   - In particular, the test sets typically contain only morphed images generated with the same tools as the images in the training set
	   - Consequently, the low error rates reported in these publications may simply reflect an overfitting to the specific and unrealistic properties of the images used. 
	   - **This suspicion is supported by the recent results of the Face Recognition Vendor Test (FRVT) MORPH test [22] conducted by the National Institute of Standards and Technology (NIST), where none of the submitted algorithms achieved satisfactory performance for all test scenarios**

**Proposal(brief)**:
- One of the greatest issue regarding existing differential MAD algorithms is that they can not cope with the large intra-class variance that must be expected for realistic probe images. 
	- Deep face recognition networks, however, have shown that they are able to work very robustly, even on challenging data. 
	- Therefore, **we propose to employ deep face representations extracted by such deep face recognition systems for differential MAD**
- we use the following deep face recognition systems: 
	- ArcFace [52], an up-to-date network with a topology optimized for automatic facial recognition 
	- The commercial face recognition SDK from Eyedea7 
	- A re-implementation8 of the FaceNet algorithm [53]
**Method(long)**:
- We use the pre-trained deep face recognition networks as feature extractors 
- and train our MAD algorithms on the deep representations extracted by the neural network (on the lowest layer)
- For the classifier, we tested various machine learning algorithms, namely AdaBoost, Random Forest, Gradient Boosting and SVM. Consistently, 
- SVM with radial basis function as kernel showed the best accuracy and was, thus, chosen for the MAD algorithm.
![[Pasted image 20231002130948.png|400]]
**remarks**
- It is shown that algorithms based on deep face representations can achieve very high detection performance (less than 3% D-EER) and robustness with respect to various post-processings.
- Finally, the limitations of the developed methods are analyzed.
- Whether a system is susceptible to this kind of attack can be theoretically examined with the framework presented in [5] and [6].
- Focuses on passport images 
- 
**references to detection methods**
- The vulnerability of automated face recognition systems against such a Morphing Attack (MA) was initially showcased in [4]
# Summary
Main contributions
1. A conceptual categorization of published MAD approaches, along with a more detailed survey of relevant differential MAD schemes.
2. The creation of a face database containing a large number of ICAO-compliant bona fide and morphed reference images, as well as corresponding unconstrained probe images, which are obtained from different image sources.
3. The use of image post-processings which are likely to be applied in the real world, i.e., JPEG2000 compression or print-scan transformations, together with the selection of probe images exhibiting variations in facial pose and expression as well as illumina                                                                                                                   cc tion and focus, enabling the training and testing of MAD algorithms in a realistic scenario.
4. The proposal of differential MAD based on deep face representations, which employs state-of-the-art face recognition systems to extract rich and compact deep facial representations from pairs of reference and probe images and combine them to train machine learning-based classifiers to detect image alterations induced by morphing algorithms.

Proposal:
- This paper proposes a comprehensive approach to detecting morphing attacks on facial recognition systems, using a realistic database for training and testing.
- The proposed approach includes a vulnerability assessment of SOTA FR systems against morphing attacks, followed by a scenario-based evaluation of the proposed MAD concept applying a commercial and two open-source deep face recognition systems.
- The paper proposes a differential MAD based on deep face representations, which employs  SOTA FR systems to extract rich and compact deep facial representations from pairs of reference and probe images and combine them to train machine learning-based classifiers to detect image alterations induced by morphing algorithms.
- The results show that these methods can achieve very high detection performance and robustness with respect to various post-processings.