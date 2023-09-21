#Pub2020 
# Information 
Title: Deep Face Representations for Differential Morphing Attack Detection

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