#JointCNN #DetectionModel 
#Pub2020 #PhysicalDomain

# Summary 
Proposal:
- a face spoofing framework specifically designed to detect unknown spoof types
- SSR-FCN
- A FCN is first trained to learn global discriminative cues and automatically identify spoof regions in face images. 
- The network is then fine tuned to learn local representations via regional supervision.
- once deployed the model can automatically locate regions where spoofness occurs and provide a final spoofness score.

Main contributions 
- We show that features learned from local face regions have better generalization ability than those learned from the entire face image alone. 
- We provide extensive experiments to show that the proposed approach, SSR-FCN, outperforms other local region extraction strategies and state-of-the-art face anti- spoofing methods on one of the largest publicly available dataset, namely, SiW-M, comprised of 13 different spoof types. The proposed method reduces the Equal Error Rate (EER) by (i) 14% relative to state-of-the-art [20] under the unknown attack setting, and (ii) 40% on known spoofs. In addition, SSR-FCN achieves competitive per- formance on standard benchmarks on Oulu-NPU [18] dataset and outperforms prevailing methods on cross- dataset generalization (CASIA-FASD [13] and Replay- Attack [12]). 
- The proposed SSR-FCN is also shown to be more inter- pretable since it can directly predict which parts of the faces are considered as spoofs.

Training 
- training is done in two stages 
1. Training FCN globally 
2. Training FCN on Self-Supervised Regions 

Datasets
- [[SiW-M]]
- [[Oulu-NPU]]
- [[CASIA-FASD]]
- [[Replay-attack]]

Metric
- ACER = (max{C}(APCER_c) + BPCER)/2, c is the number of spoof types 
- EER
- TDR at 2.0% FDR
- confusion matrix w. TP, TN, FP and FN
- APCER = FN/(FN+TP)
- BPCER = FP/(FP+TN)
- HTER = (FDR + FRR)/2

SOTA landmark detector 
- DLIB [57]


# PDF Article
![[SSRFCN Look locally infer globally - A generalizable.pdf]]
