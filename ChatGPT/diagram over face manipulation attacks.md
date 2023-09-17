Grobe auffassungvon mir 

```mermaid
graph TD
    subgraph Manipulation_Attacks
        A[Manipulation Attacks]
    end

    subgraph Domains
        C1[Digital]
        C2[Physical]
        C3[Adversarial]
    end

    subgraph Attack_Techniques
        E1[Face Swap]
        E2[Morphing]
        E3[3D Mask]
        E4[obfuscation]
    end

    subgraph Attack_Types
        G1[Face2Face]
        G2[FaceSwap]
        G3[Silicone Mask]
    end

    
    A --> C1
    A --> C2
    A --> C3
    C1 --> E1
    C1 --> E2
    C2 --> E3
    C3 --> E4
    E2 --> G1
    E1 --> G2
    E3 --> G3
```
# CHatGPT
```mermaid
graph TD
    subgraph Manipulation_Attacks
        A[Manipulation Attacks]
    end

    subgraph Domains
        C1[Digital]
        C2[Physical]
        C3[Adversarial]
    end

    subgraph Attack_Techniques
        E1[Face Swap]
        E2[Morphing]
        E3[3D Mask]
        E4[Obfuscation]
        E5[Reenactment]
        E6[Style Transfer]
        E7[Audio-Visual Manipulation]
    end

    subgraph Attack_Types
        G1[Face2Face]
        G2[FaceSwap]
        G3[Silicone Mask]
        G4[Deepfake]
        G5[Impersonation]
        G6[Identity Theft]
        G7[Voice Cloning]
    end

    A --> C1
    A --> C2
    A --> C3
    C1 --> E1
    C1 --> E2
    C1 --> E4
    C2 --> E3
    C3 --> E1
    C3 --> E7
    E1 --> G1
    E1 --> G2
    E2 --> G3
    E2 --> G4
    E3 --> G4
    E4 --> G5
    E4 --> G6
    E7 --> G7
    E7 --> G5
    E7 --> G6

```