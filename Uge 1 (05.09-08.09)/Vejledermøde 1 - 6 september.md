
# Next steps 

### 1. NDA and Data (DONE)
- Mathias sender en NDA som jeg skal underskrive for at få adgang til deres data. 
- Send ham det underskrevede dokument i løbet af i dag. 

### 2. Meetings
- fremadrettet holder vi møde onsdag kl 10. 
- vi holder ikke møde næste onsdag, dvs. den 13 
- I stedet for sender jeg en opsummering af det jeg har lavet i løbet af ugen næste onsdag senest fredag. 
- Kan til enver tid skrive til mathias, han plejer at svare hurtigt

### 3. Ideer til starten
- start med at læse op på related work, relevante emner er 
  1. computer vision detekteringsmetoder
     - etableret ældre 
     - state-of-the-art i.e. nyt 
  2. dyb læring
     - etableret ældre, mathias artikel og lignende 
     - state-of-the-art i.e. nyt 
  3. relaterede detection topics 
     - dokument falsk
     - mediaforensics in general 

-  lav en tabel over eksisterende manipulationsdetekterings metoder 
  - inkluder fordele og ulemper 
  - baserede på denne analyse skulle du gerne finde på en retning til dit speciale. 

- identificer relevante manipulationer
  - det burde ikke være alt for mange
  - hellere 1-2 ekstra og så tilføj mere i løbet af projektet hvis relevant 

- se på differential detection vs. no-refrence detection 
  - evtl argumenter yderligere for dit valg af differential detection. 

### 4. Uge 2 eller 3 
- efter jeg har set på related work og læst en masse i uge 1 og 2. 
- Nu er dte relevant at få kigget på noget data til projektet og det kode mathias stiller til rådig, få en følelse for det for at inkludere relevante kommentarer i projektbeskrivelsen. 
- 
# Spørgsmål

- forventningsafstemning til det endelige produkt: ifht. hele konceptet hvilke dele skal jeg fokusere mest på, 3 forskellige steder hvor der er brugt AI modeller. 

- Grov plan for de næste 6 måneder
  - litterature review 
  - lab: modellering + analyse
  - rapport skrivning (hele februar måned)

- Hvilke AI modeller er det relevant at se på ? mange forskellige bliver nævnt i artiklerne 

- ideer til hvor jeg kan finde andre attack metoder, indtil videre har jeg kun set dem du også nævner i din artikel. 

# Mathias 

### 1. Praktisk om specialet 
- sencor kommer til at have generel viden om cyber sikkerhed. Evtl husk at komme specialet ind i the big picture af cybersikkerhed ? sammenlign failure på manipulation detection med cyber sikkerhed ifht. hackers ? 

- Project plan skal afleveres indenfor den første måned, for mit vedkommende **d. 4 oktober** 
- Mathias sender sin projectplan fra dengang som retningslinbje. 
- Han har selv kommenteret på at den er forholdsvis lang

### 2. Project plan indhold
- idee: Fra den mere generel projekt indberretelse skal projektplanen definere fokusområder for mit special, dvs. indenfor face manipulation detection af impersonation attacks. 
- motivation, inkluder noget baggrundsviden om problematikken, referencer etc. 
- beskrive hvilke tilgange der udforskses. 
- hvordan løser jeg disse problemer 
- research questions 
- related work, dette må som sådan genbruges til thesis og er derfor en god idee at skrive allerede nu. 

### 3. brain dump 

- physical domain attacks: make up, silicone mask and (print and replay attack)

- state-of-the-art computer vision metoder er visiontransformer og 

- generaliseringsmetoder vi kan kigge på er
  1. anomaly detection, dette har mathias set på i sin artikel 
  2. dynamisk thresholding ved at se på embedding space
  3. ensemble learning
  4. sikkert mere som jeg kan finde 

- ulemper ved anomaly detection
  - vi kender ikke den specifikke attack n¨r vi identificere en attack
  - den score der bruges til at identificere attack er ikke baseret på de forskellige attacks 
  - den metode mathias har set på er ikke så avanceret, kan udvides her 

- hvorfor se på embedding space ? 
  - NOTE: embedding space referer til de sidste layers i et DNN hvor der plejer at være et FFNN, tænk på det som i NLP hvor konge og dronning er tæt på i den ene dimension(penge/hierarchi) men langt væk i den anden(gender)
  - embedding space giver clusters for de forskellige attacks eller mennesker ? 
  - vi kan derfor bruge dynamiske score alt efter hvad for en cluster et billedesæt bliver tildelt. 
  - en morphing attack behøver måske en mindre score for at identificeres som attack end en faceswap 
  - hvordan kan man forbinde dette med bayesian ML ? har det ikke noget med densitet at gøre ? 

- state-of-the-art computer vision methods som jeg burde se på 
  1. visiontransformers 
  2. diffusiontransformers 

