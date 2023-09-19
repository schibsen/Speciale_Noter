https://en.wikipedia.org/wiki/Viola–Jones_object_detection_framework

- a machine learning object detection framework proposed in 2001 by Paul Viola and Michael Jones. 
- It was motivated primarily by the problem of face detection, although it can be adapted to the detection of other object classes.

Viola–Jones is essentially a [boosted](https://en.wikipedia.org/wiki/Boosting_(machine_learning) "Boosting (machine learning)") [feature learning](https://en.wikipedia.org/wiki/Feature_learning "Feature learning") algorithm, trained by running a modified [AdaBoost](https://en.wikipedia.org/wiki/AdaBoost "AdaBoost") algorithm on [Haar feature](https://en.wikipedia.org/wiki/Haar-like_feature "Haar-like feature") classifiers to find a sequence of classifiers[f_{1},f_{2},...,f_{k}](https://wikimedia.org/api/rest_v1/media/math/render/svg/33f5b5d94c2f6f9144c9fc91c11fcae2648261db). Haar feature classifiers are crude, but allows very fast computation, and the modified AdaBoost constructs a strong classifier out of many weak ones.
