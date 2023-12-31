Title: Face X-ray for More General Face Forgery Detection
# Info

**Publication**:
- 2020
**differential**:
- NO
**no-reference**:
- YES
**Datasets**:
- 
**performance**:
- AUC, AP, EER
![[Pasted image 20231002142637.png|Table 2. Benchmark results in terms of AUC, AP and EER for our framework and the state-of-the-art detector Xception [36] on unseen datasets. Our framework, trained using the blended images, already performs better than the baseline. The performance is further greatly improved in most cases if we exploit additional fake images even not from the same distribution as the test set.]]
**attacks**:
- digital: those that use blending, i.e. not synthetic generated ones
**Motivation(if relevant)**
- We observe that most existing face manipulation methods share a common step: blending the altered face into an existing background image.
- Our focus in this work is the problem of detecting face forgeries, such as those produced by current state-of-theart face manipulation algorithms including 
	- DeepFakes [1], 
	- Face2Face [46], 
	- FaceSwap [2], and 
	- NeuralTextures [45].
- Most existing works [12, 44, 25, 35, 36] detect face manipulation in a supervised fashion and their methods are trained for known face manipulation techniques. 
	- For such face manipulation, these detection methods work quite well and reach around 98% detection accuracy. 
	- However, these detection methods tend to suffer from overfitting and thus their effectiveness is limited to the manipulation methods they are specifically trained for
	- When applied to forgery generated by unseen face manipulation methods, these detection methods experience a significant performance drop.
	- These discrepancies make the boundaries fundamentally detectable.
	  ![[Pasted image 20231002140000.png|400]]
	- Instead of capturing the synthesized artifacts of specific manipulations in the second stage, we try to locate the blending boundary that is universally introduced in the third stage.
	- Our approach is based on a key observation: when an image is formed by blending two images, there exist intrinsic image discrepancies across the blending boundary.
**Proposal(brief)**:
- we propose a novel image representation called face X-ray for detecting forgery in face images
- The face X-ray of an input face image is a greyscale image that reveals whether the input image can be decomposed into the blending of two images from different sources.
- It does so by showing the blending boundary for a forged image and the absence of blending for a real image. 
- Face X-ray is general in the sense that it only assumes the existence of a blending step and does not rely on any knowledge of the artifacts associated with a specific face manipulation technique. 
- Indeed, the algorithm for computing face X-ray can be trained without fake images generated by any of the state-of-the-art face manipulation methods
- The key observation behind face X-ray is that *most existing face manipulation methods share the common step of blending an altered face into an existing background image*, and there exist intrinsic image discrepancies across the blending
**Method(long)**:
- For an input face image, its face X-ray is a greyscale image that can be reliably computed from the input. 
- This greyscale image not only determines whether a face image is forged or real, but also identifies the location of the blending boundary when it exists
**remarks**
- ***Image fogery classification***
  Image forgery detection is mostly regarded as merely a binary (real or forgery) classification problem. Early attempts [30, 16, 17] aim to detect forgeries, such as copy-move, removal and splicing that once were the most common manipulations, by utilizing intrinsic statistics (e.g., frequency domain characteristics) of images. However, it is difficult to handcraft the most suitable and meaningful features. With the tremendous success of deep learning, some works [10, 33, 7] adopt neural networks to automatically extract discriminative features for forgery detection
**references to detection methods**
- Some recent works [49, 13] have noticed this problem(problems with generalization) and attempted to capture more intrinsic forgery evidence to improve the generalizability. However, their proposed methods still rely on the generated face forgeries for supervision, resulting in limited generalization capability.
- This makes face forgery detection increasingly challenging, attracting a large number of research efforts [12, 44, 25, 32, 28, 18, 3, 22, 35, 36].
	- , a face forensic approach exploiting facial expressions and head movements customized for specific individuals is proposed in [4].
	- FakeSpotter [47] uses layer-wise neuron behavior instead of only the last neuron output to train a binary classifier. 
	- To handle new generated images, an incremental learning strategy is introduced in [27]. 
	- Lately, FaceForensics++ [36] provides an extensive evaluation of forgery detectors in various scenarios.
**references to localization manipulation methods**
- Early works [37, 8, 15] reveal the tampered regions using manually designed low-level image statistics at a local level. 
- Subsequently, deep neural network is introduced in image forgery localization, where most works [5, 40, 29, 38] use multi-task learning to simultaneously detect the manipulated images and locate the manipulated region
- Stehouwer et al. [41] highlight the informative regions through an attention mechanism where the attention map is guided by the groundtruth manipulation mask.
- Bappy et al. [6] present a localization architecture that exploits both frequency domain and spatial context.
**references to lack of generalizability**
- it has been noted in recent works [19, 11, 49, 13, 23] that the performance of current methods drop drastically on forgeries of new types
	- Xuan et al. [49] use an image preprocessing step to destroy low level unstable artifact, forcing the network to focus on more intrinsic forensic clues. 
	- ForensicTransfer [11] proposes an autorencoder-based neural network to transfer knowledge between different but related manipulations. 
	- LAE [13] also uses autorencoder to learn fine-grained representation regularized by forgery mask supervision.
# PDF 