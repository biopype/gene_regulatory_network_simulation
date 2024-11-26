# BRCA1 Regulatory Network Analysis Using Ordinary Differential Equations (ODEs)

## Scope of the Project
In this project, we aimed to develop a protein-protein interaction network of the BRCA1 protein and analyze its dynamic regulatory mechanisms using Ordinary Differential Equations (ODEs).

## Outline of the Steps
We began by obtaining a gene network dataset for BRCA1 from the STRING database. Individual genes were represented as **nodes**, and their regulatory relationships were modeled as **weighted edges**. The weights were determined by a combined interaction score, which reflects the strength of protein-protein interactions. Regulatory dynamics were assessed through metrics such as **co-expression**, **gene fusion**, and **chromosomal proximity (neighborhood)**, which helped identify whether the interactions were repressive or activating.

![image](https://github.com/user-attachments/assets/75edf8ed-db5c-48f2-9004-0428394a5a9c)

#### Fig 1: Weighted protein interaction network based on confidence score 

## Filtering Interactions
A critical step in this project was filtering interactions to retain only high-confidence connections. Interactions with a **combined score above 0.8** were prioritized, especially those supported by **experimental evidence** or **database annotations**. This filtering ensured that downstream modeling and analysis focused on biologically relevant interactions for the BRCA1 protein.

## Ordinary Differential Equations (ODEs)
The dynamic behavior of the system was modeled using Ordinary Differential Equations (ODEs). Protein concentrations (xi) were described over time using equations that incorporated interaction strengths (αji) and their regulatory effects. Activation relationships increased protein concentrations, while repression relationships decreased them.

### General Form of the ODE
![image](https://github.com/user-attachments/assets/db476929-f796-45ab-9825-bc1d2daf1ae1)

Here:
- αji represents the interaction strength from protein j to protein i.
- The term ∑j (αji ⋅ xj) captures the net influence of other proteins on xi.
- −xi represents the natural degradation of xi over time.

By solving these equations numerically, we simulated the dynamic changes in protein concentrations, gaining insights into the temporal behavior of the network.
![image](https://github.com/user-attachments/assets/b7e3b663-5627-46e0-9df6-f563279487a9)


#### Fig 2: Dynamic protein network model

### Network Visualization
The network was visualized to integrate multiple interaction metrics such as the **combined score**, **gene fusion**, and **coexpression**. 
- Node sizes were scaled based on the **degree** (number of interactions).  
- Edge thickness represents **interaction strength**
- Color represents **coexpression levels**


![image](https://github.com/user-attachments/assets/f10c2b08-a258-4598-a8f9-cbdfe22d82b5)

#### Fig 3: Protein-protein interaction network based on combined score

![image](https://github.com/user-attachments/assets/9bf97e77-a5f6-44c9-9288-6f7113abdc7d)

#### Fig 4: Enhanced protein-protein interaction network incorporating coexpression and gene fusion

## Key Observations
- Proteins like **BRCA1** and **BARD1** exhibited strong coexpression, indicating tight regulatory interactions.
- Proteins like **BABAM1** and **UMC1** showed weaker coexpression.
- **BRCA1** appeared as a highly connected node, acting as a hub within the network.

## Biological Implications
- Proteins with higher coexpression levels (toward the **yellow spectrum**) are functionally related.
- Hub proteins like **BRCA1** play critical roles in maintaining network stability and mediating significant interactions.

## Conclusion
This project demonstrated the utility of ODEs in modeling complex biological systems such as protein-protein networks. By simulating regulatory processes, we gained valuable insights into protein interactions' roles in cellular behavior and disease. The integration of mathematical modeling with computational network analysis deepens our understanding of gene regulatory mechanisms.
