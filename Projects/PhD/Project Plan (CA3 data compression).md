- [https://sites.uci.edu/mcnaughtonlab/people/bruce/talks/learning-and-memory-2018/](https://sites.uci.edu/mcnaughtonlab/people/bruce/talks/learning-and-memory-2018/)

## Tools
### Visualize Neural Network 
- activation maximization to get information about cells influencing result
- Partial Dependence Plot
- 
## Intro
The hippocampus, a vital brain region, plays a central role in memory formation, spatial navigation, and cognitive processes. In this project, we aim to delve into the mechanisms underlying environmental information compression within the hippocampus and how this compressed information can be used for future prediction. Compression and noise filtering is crucial for survival, since it increases the efficiency and speed of information transmission, which is used for planning. Specifically, we will address the following questions:

- **Encoding and Compression**: How does the hippocampus encode and compress sensory information to create a spatial map?
- **Noise Filtering Strategies**: What strategies allow the hippocampus to filter out noise from other sensory or internal inputs?
- **Predictive Precision**: To what extent can future predictions be made based on the compressed information?
- **Cellular Decision-Making**: Which specific cells are responsible for determining how information is compressed?
## Background
### Hippocampus Structure
1. Hippocampus is a central hub![[Pasted image 20240219150233.png]]
2. Spatial Code![[Pasted image 20240222113329.png]]
## Methods
### Dimension Reduction
#### Linear PCA
#TODO 
#### Non-Linear T-SNE/UMAP
#TODO 
### Classification/Prediction
#### Decision Forest
#TODO 
#### Neural Networks/ Auto-Encoders
#TODO 
### Noise Filtering 
#TODO 
## Data
### Characterize Environmental Information Encoding:
Analyze existing imaging datasets to identify patterns of hippocampal activity related to environmental cues. We will focus on the following datasets:
1. 0D Environments:
	1. Steffen (CA3): Explore intrinsic neuronal activity.
3. 1D Environments:
	1. Anja (MEC): Investigate how hippocampal neurons encode space and speed perception.
	2. Renan (MEC, M1): Study cell identity change manifolds in virtual reality (VR).
4. 2D Environments:
	1. Nathalie’s (CA3): Mouse in a Box with changing shapes
### Noise Filtering Mechanisms 
Investigate how the hippocampus filters out noise from other sensory or internal inputs. We will explore:

1.       Catalin (CA3): Investigate volitional control of cells.
2.       Nathalies (CA3): Mouse with cookie crumps
3.       Talia (CA3): Fear-conditioning in a rotating Environment
# Other Peoples Projects

| Name     | Area    | Img | Manipulation      | Q                                                               | E                     | Dim |
| -------- | ------- | --- | ----------------- | --------------------------------------------------------------- | --------------------- | --- |
| Anja     | MEC     | 2P  | DTX               | space/speed propriception                                       | Wheel                 | 1D  |
| Steffen  | CA3     | 2P  | -                 | intrinsic correlation                                           | wheel                 | 1D  |
| Steffen  | CA3     | 2P  | shuffle           | rigid plastic place cells                                       | Treadmil              | 1D  |
| Renan    | MEC, M1 | 2P  | VR                | cell identity change manifolds                                  | VR, BMI               | 1D  |
| Catalin  | CA3     | 2P  | VR                | volitional control of cells                                     | BMI                   | 1D  |
| Vilde    | CA3     | 2P  | -                 | hippocampus support memory traces                               | VR, BMI               | 1D  |
| Nathalie | CA3     | 1P  | Fear              | plasticity change network dynamics/maps?                        | Box + ?               | 2D  |
| Nathalie | CA3     | 1P  | -                 | box shapes plasticity change network dynamics/maps?             | transformable box     | 2D  |
| Talia    | CA3     | 2P  | Fear              | Episodic memories                                               | Tone, smell, box, pot | 1D  |
| Maria    | CA3     | -   | Fear              | active avoidance                                                | circular env          | 2D  |
| Maria    | CA3     | -   | Fear, Chemo, Opto | Persistence and reinstatement of infant memories in adult brain | box, circle, pot      | 2D  |





## Anja (MEC)
DTX representation of space/speed without proprioception
## Steffen (CA3)
Intrinsic Imaging, Rigid Plastic
## Renan (MEC, VR-BMI-VR): 		
Q:
1. do mice perceive the corridors as different environments?
2. Identify stable correlated network 
Is it possible to break an attractor or remove/add cells of the attractor based on BMI tuning? 
What happens with those cells?
E:
## Talia
## Maria
1. Stable memory trace from infancy to adulthood
2. Active infant memory trace required for reinstatement
3. Comparison to adult silent memory traces
4. Active infant memory trace required during OFFLINE consolidation
5. Activity tuning of infant traces during memory reinstatement
6. Which brain areas are involved in memory reinstatement – bring silent infant traces into dormant state?
## Catalin
## Vilde ()
Q: How does the hippocampus support dynamic memories?
1. Time Changes a memory's 
	1. attributes![[Pasted image 20240219150029.png]]
	2. plasticity![[Pasted image 20240219145912.png]]
	3. brain-wide engram![[Pasted image 20240219150059.png]]
## Nathalie (CA3)

Question asked: Does an experience of which we know that it induces plasticity in CA3 change network dynamics and the way the network maps environments?  
Type of experiment: 1p calcium imaging (miniscope) in 2D environments. See attached powerpoint for detailed protocols.  
Brain area: CA3
![[Pasted image 20240222131633.png]]
![[Pasted image 20240222131618.png]]