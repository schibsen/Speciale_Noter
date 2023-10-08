
# MAD 
[^1]: [[First Differential Detection introduction]]

Single image MAD approaches can be categorized as 
1. texture descriptors, e.g., in [23], 
2. forensic image analysis, e.g., in [24], 
3. and methods based on deep neural networks, e.g., in [25]. 
These differ in the artefacts they can potentially detect

**Texture descriptors** 
- e.g., Local Binary Patterns (LBP) [26] or Binarized Statistical Image Features (BSIF) [27], attempt to *extract discriminative information from images*, which can be employed for the purpose of texture classification. 
- The morph process averages the images, which results in smoothed skin textures. 
- Furthermore, ghost artefacts or half-shade effects can occur due to regions that do not overlap exactly (e.g., hair).
- In particular, in the area of the pupils and nostrils these artefacts appear more frequently, for examples the reader is referred to [28]. 
- In addition, distorted edges or shifted image areas can occur. 
- These types of artefacts can be easily represented and detected using texture descriptors in multiple ways [7], [20], [21], [23], [29]–[37].

**forensic image analysis**
- Under the assumption that the morphing process leaves specific traces in the image, forensic image analysis techniques can be used to detect them. 
- By averaging the images, the sensor pattern noise is changed. 
- It was shown in [38]–[42] that these changes can be used for MAD. 
- Under the assumption that the images are intermediately stored during the morph creation process employing lossy compression algorithms, double compression artefacts can be analyzed [17], [43]. 
- Furthermore, inconsistencies in the image, e.g., inconsistent illumination [44] or color values, might be evaluated

**Deep Neural networks**
- can be used to detect morphs in two different ways. 
- Firstly, a new neural network is trained from scratch or an existing neural network is re-trained [19], [25], [45] for the task of MAD. 
	- Deep neural nets can theoretically be trained to detect any artefact. 
	- Therefore, it is important that the training data contains a high variance, to avoid overfitting to algorithm and database specific artefacts. 
- Secondly, the feature vectors (embeddings) extracted by existing deep nets can be employed for MAD [34]. 
	- Since the neural network was not trained on morphed facial images, it can be assumed that no overfitting to unrealistic morphing artefacts occurs.