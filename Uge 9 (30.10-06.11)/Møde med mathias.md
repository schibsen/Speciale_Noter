
Mål vi kan have med modellen
- lightweight: 
- explainability


To Do 
- benchmarks
- - choose different backbones 
- - choose different classification models 
- - antaget hypothese : der sker ikke så meget 
- - evtl tilføj: vision transformers 

standard størrelse ArcFace Resnet100

Different datasets for different backbones 
- since focus on fair AI, use a dataset som ikke er blevet retracket 
- MS1M, er blevet scrapet for lang tid siden, det er ikke opensource længere 
- vælg e

Performance benchmark
- har forskellige FR systemeer, ifht loss funktioner 
- og ifht hvor light, normal or heavy weight modellerne er
- ViT med ind i backbone 
- 2 LW(mobileNet GhosNet), 2LW(ArcFace Resnet100, ViT) 

- EER, DET and Accuracy , face swapping og morphing 
- outer faceswap: first id against probe
- inner faceswap: second id against 