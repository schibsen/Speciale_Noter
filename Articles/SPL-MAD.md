# Title
Unsupervised Face Morphing Attack Detection via Self-Paced Anomaly Detection


#Pub2022 #DetectionModel #Unsupervised #NoReference

#DigitalManipulation #AnomalyDetection


# Summary
Proposal:
- a completely unsupervised MAD solution via self-paced anomaly detection
- by leveraging the existing large-scale face regocnition datasets


Introduction
- only 1 single image based \[8\] and 1differential based MAD method \[28\] were proposed to detect morphing attacks as anomalies by training a one-class classifier 
- **Problem trying to be solved**:  we cannot be certain that the publicly available datasets for MAD only consist of bona-fide images, thus training a supervised model (as has been done until now) uses the false assumption that the training data does not include an attack. Thus leading to false results. 
- Comment on previous note: 
  1. first argument: The public available MAD data is low. 
  2. 2nd arg.: more data is needed to improve detection, especially unseen attacks
  3. 3rf arg.: the number and size of publicly available face recognition datasets is large
  4. 4th arg.: since FR datasets are pulled from the internet they might unintentionallt contain manipulated face images. 
  5. 5th arg.: therefore we propose our method, unsupervised which should align for that. 

Main contributions
1. We first study the behaviour of unsupervised anomaly detection through reconstruction error analysis on MAD data to ensure that our unsupervised MAD solution is developed on the base of solid empirical analysis. 
2. We leverage our abovestated observation to present a novel unsupervised MAD solution via an adapted self-paced anomaly detection, namely SPL-MAD.
3. The experimental results demonstrate that our SPL-MAD solution not only reaches the performance of supervised MAD solutions but also outperforms well established supervised MAD methods.


# PDF article 
![[Unsupervised_Face_Morphing_Attack_Detection_via_Self-paced_Anomaly_Detection.pdf]]

# More