# My original version 
### Motivation and Project Description 

Many security systems today rely on Face Recognition as a security measure. Such security measures are, for example, encountered in border control, at the airport, on your mobile device, tablet or computer and many more. 
It is, therefore, of utmost importance to ensure that the Automatic Face Recognition(AFR) systems used in these scenarios are secure and robust against Attacks. 
The Detection of attacks has, therefore, been a significant topic in research, resulting in many different detection methods. 
When discussing Attacks on AFR systems, there are three main Domains: Presentation or Physical Attacks, Digital Attacks and Adversarial Attacks. 
Each Domain contains several attack types; in the Physical Domain, there is the 3D Mask, and in the Digital domain, there is a Morphing attack. There are realisations for each attack type; in the case of the 3D Mask, this could be a transparent mask or a silicone mask, whereas, in the case of Morphing, different morphing models represent different realisations of a specific attack type, a single realisation is defined by the model, the training data, the optimiser and the loss function, since each parameter results in a different outcome of attacks. A visualisation of the connection between attack domains, attack domains and realisations is presented in Figure 1. 

Most of the early work on Attack Detection in AFR systems focused on one of the three domains, resulting in them generalising poorly to unseen attacks, especially those of the other domains. Therefore, most recent research focuses on models that generalise well to two or all of the three domains and unseen attacks. 
The last part, generalising well to unseen attacks, is of utmost importance, as it has to be assumed that the various attack types in action are unknown during training. 




# My adapted version 

### Motivation and Project Description 
Many security systems today rely on Face Recognition as a cornerstone for safeguarding various domains, including border control, airport security, device access, and more. 
It is, therefore, of utmost importance to ensure that the Automatic Face Recognition(AFR) systems used in these scenarios are secure and robust. 

The Detection of attacks has, therefore, been a significant topic in research, leading to the development of numerous detection methods. \[cite some detection methods\]
Attacks on AFR systems face attacks across three domains: Presentation or Physical Attacks, Digital Attacks and Adversarial Attacks. 

Within each of these domains, multiple attack types manifest. 
For instance, in the physical Domain, an attack type is 3D Masks. 
Each of these attack types can have several manifestations; for the 3D mask, one is a transparent silicone mask, and another is a standard silicone mask. 
Figure 1 shows the connection between attack domains, attack types, and their manifestations.

Most of the early work on Attack Detection in AFR systems focused on a single domain, resulting in them generalising poorly to unseen attacks, especially those from other domains. Consequently, recent research shifted towards developing better generalisation capabilities, spanning two or all three attack domains and previously unseen attacks. 





# Chat update 
### Motivation and Project Description 

In today's security landscape, Face Recognition stands as a cornerstone for safeguarding various domains, including border control, airport security, mobile device access, tablets, computers, and more. Ensuring the security and resilience of Automatic Face Recognition (AFR) systems used in these critical scenarios has become a paramount concern.

Detecting and mitigating attacks on AFR systems has emerged as a focal point in research, leading to the development of numerous detection methodologies. Attacks on AFR systems can be broadly categorized into three main domains: Presentation or Physical Attacks, Digital Attacks, and Adversarial Attacks.

Within each of these domains, multiple attack types manifest. For instance, in the Physical Domain, the use of 3D masks is one form of attack. In the Digital Domain, morphing attacks pose a distinct threat. Each attack type can have various realizations, adding to the complexity of threat detection. In the case of 3D masks, these realizations encompass transparent and silicone masks. Meanwhile, different morphing models represent distinct realizations of the morphing attack, with each model's outcome being influenced by factors like the training data, optimizer, and loss function. A graphical representation illustrating the relationships between attack domains and their realizations is depicted in Figure 1.

Traditionally, research efforts in Attack Detection for AFR systems often focused on a single domain, limiting their ability to generalize effectively to unseen attacks, especially those from other domains. Consequently, recent research has shifted towards developing models with superior generalization capabilities, spanning two or all three attack domains and accommodating previously unobserved threats.

The significance of this research lies in its capacity to adapt and safeguard against unforeseen attacks, as it must be assumed that new, diverse attack types may arise during system operation, making the ability to generalize to previously unencountered threats a critical requirement.