 Importance Order
1. General
	1. PhD
	2. Lab
2. Code Fix
3. Projects
	1. Open Field Dynamics
	2. Intrinsic Imaging 
	3. Box Shapes
	4. Rigid Plastic
	5. Own
4. Read
5. Code Improve
	1. Speed
	2. Nice to have
# General
## PhD   
- How does priming happen? 
	- does it influence memory creation decision? 
		- it is known that there is a 6h windows that links everything into one memory
- What is happening inside grooming?
	- Add Nathalies Grooming detection code
	- Are fear memory cells activated? Would be out of context activation

### Continue here
- structure index
	- check if moving and stationary periods files are saved properly
	- Do a permutation test for significance between sessions
	- check if structure index decreases over time ( positional representation decreases over time in stationary periods )
	- add random shuffling result to plot
	- labels time + Color cebra plot by time to check point distribution

- shape similarity
	- only use place cells (directional! only first to second dataset)
	- add self reference normalization to remove noisyness
	- analysis possibility:
		- centroid distances and std ?
			- how ist std changing?

	- How is MDS seperating?
		- find axis meaning 
			- always the same axis meaning? $\rightarrow$ is regression possible?
		- Make plots like Talias PR (15.07.2025)
			1. plot MDS space
			2. plot correlation with mds dimension 1
				1. direct comparisson cFC vs NS 
			3. plot mds dimension 1 as x-axis and experience days in box (should be 4 lines FS/NS/cFC/)

	- Use Nathalies way to calculate cell tuning maps

	- read:
		- [Soft Matching Distance: A metric on neural representations that captures single-neuron tuning](https://proceedings.mlr.press/v243/khosla24a) 
		- [Generalized Shape Metrics on Neural Representations](https://proceedings.neurips.cc/paper_files/paper/2021/file/252a3dbaeb32e7690242ad3b556e626b-Paper.pdf)
- Position derivative for noisy frames
	- [https://onlinelibrary.wiley.com/doi/10.5402/2011/164564](https://onlinelibrary.wiley.com/doi/10.5402/2011/164564)It is the method I used to apply the derivatives on the Calcium traces of C. Elegan's neurons, but it is a general and elegant way to compute the derivative of a noisy signal."In many scientific applications, it is necessary to compute the derivative of functions specified by data. Conventional finite-difference approximations will greatly amplify any noise present in the data. Denoising the data before or after differentiating does not generally give satisfactory results (see an example in Section [4](https://onlinelibrary.wiley.com/doi/10.5402/2011/164564#sec-0004)).  
	- A method which does give good results is to regularize the differentiation process itself. This guarantees that the computed derivative will have some degree of regularity, to an extent that is often under control by adjusting parameters. A common framework for this is Tikhonov regularization [[1](https://onlinelibrary.wiley.com/doi/10.5402/2011/164564#bib-0001)] of the corresponding inverse problem. That is, the derivative of a function _f_, say on [0, _L_], is the minimizer of the functional"

- Feature Similarity
	- representation of features is precise?
	- Read this paper to check how they extract information represented features in manifolds
		- Zotero: [Neural Manifold Capacity Captures Representation Geometry, Correlations, and Task-Efficiency Across Species and Behaviors](https://www.biorxiv.org/content/10.1101/2024.02.26.582157v1.full.pdf)
		- maybe also this https://arxiv.org/html/2503.18114v1

- Try Decoding like LaPrida
	- https://www.perplexity.ai/search/read-the-paper-and-prepare-for-JfQ1sq6OTo2ZfPMNdqw5vQ
		- La Prida used SI index in raw data space and 3D space to check if embedding algorithm is preserving the information
---
	---------------------------before PR-------------------------------------
	- make proper coloring for current plot
	- Goal:
		- see if manifold change stereotypically from 1-9
			- try to align manifolds
		- Manifold changes after Fear Conditioning?
		- Sudden change from FS9 to NS1? (cFS vs NS)
	- Do clustering and regression in High dimensional space instead of lower dimensions
		- how clustered are these sessions?
	- create proper shape similarity code in Mother
	- create clustering within one animal
	- single animal plot
		- white background 
		- RED: FS1-Fs9 (getting darker), Green: FS10-FS18 (getting lighter), BLUE: NS1-9(getting darker)
		- 
	- combined plot using mds to have a big space with a subspace for every animal

- update computer: BZ-RGFD02-PDW19

- finish proper hdf5 saving function 
	- save regularly instead of in the end
	- clean up and check how functions are working
	- add the possibility of adding columns with different names

- continue working on proper plotting
	- feature learning

- create Learning Measure evaluation analysis based on entropy
	- Cosine similarity != kde_entropy (--> mean is not that important. spread description is more valuable)
		1. combine population vectors before analysis
			1. transform all datapoints to same number of dimensions using a method (pca?)
			2. combine all vectors into one matrix
		2. Prepare data
			1. embedd into 3d space using cebra or
		3. subsample population vectors to ensure 


- Decodings
	- improve plotting of cross decoding. currently it is always plotting but it should only plot the specific levels
	- create plotting of cross decoding in lines not barplots when number of bars is too high (> 4)
		- Cross Decode
	- test XGB Decoder instead of cebra embedding and decoding afterwards
	
- Structural Index:
	- create proper color changes
	- less lines per plot by default
	- what change is significant?
	- Determine how the bins are calculated, probably split of data into 3x3 bins
	- 

- cell Assemblies
	- Dimensionality reduction
		- Principal Component Analysis (PCA), Peyrache al. 2010
		- Independenc Component Analysis (ICA), Lopes.dos.santos et al. 2013
		- Non-negacive Matrix Factorization (NMF), Mackevicious al. 2019
	- Network analysis
		- Spike Train Communities (ST C), Humphries al. 201 1
		- Markov Stability for Community Detection (MSCD), Billeh al. 2014
		- Hidden Markov Model (HMM). Maboudi et al. 2018
	- Agglomerative construction of groups
		- Cell Assemblies Detection (CAD), Russo etal. 2017

- create full base processing pipeline
- Open up CEBRA as it is already done to check contribution maps: https://grok.com/share/bGVnYWN5_a1cee7b8-bf56-492d-9729-2eba8322119d
- Next
	- Build 2 visits of location check to ensure bin is visted often enough?
	 - Do the Manifolds Cluster based on shape distance?
	 - How well does Local

Additional:
What are the communities used for?
	- define communities based on sttc percentile matrix (pearson corr. also possible)
		- networkx package: louvain algo
		


- add cell community detection using (using a dendogram and coloring result)
	- based on cosine similarity of binarized (or binarized scaled)
	- hirarchical cluster
		-- do for shape similarity?

show that it is possible to split conditions and groups
	- calculate metrics (e.g. graph metrics) for every group (control vs cFC)
	- use lda to seperate all groups
	- use silhouet score to provide a proper number for separation

Do we need plot_consistency_scores ?

### think about
- [ ] Look into transition states (moving to stationary and vice versa) using cebra
- [ ] certainty of movement sate useful?
- [ ] Think of the idea that an attractor is only representing a variable (binary (or higher) bit, analog bits (continuouse), qbit (3d))
- [ ] Habenula responsible for rotation also in mice? (paper from Ruben Portugues larval zebrafish)



# Projects

## Data Compression Information Encoding 
### Questions 
1. Is the information flowing into the hippocampus the same?
	1. If not, why is the decoder trained on the "best" day better independent of the dataset used for testing?
		1. Is the network changing? How?
### Tasks
- [ ] Extract Information about the network change
	- [ ] Look into the learned weights of the Cebra Encoder, what is the difference?
- [ ] https://sites.uci.edu/mcnaughtonlab/people/bruce/talks/learning-and-memory-2018/
	- [ ] Think+read about
		- how are we able to look into the efficiency of coding?
- [ ] LTK
	- [ ]  here you find information on what you need to do: [https://www.ltk.uzh.ch/en/Teaching-and-Training/Training/Registration-System.html](https://www.ltk.uzh.ch/en/Teaching-and-Training/Training/Registration-System.html)
	- [ ] here is the link to the course: [https://vsfltkreg.uzh.ch/course/m-1/en](https://vsfltkreg.uzh.ch/course/m-1/en) where you can click on "register": german courses [https://vsfltkreg.uzh.ch/course/m-1/de](https://vsfltkreg.uzh.ch/course/m-1/de)
## Open Field Dynamics
### Findings
1. A mature, stable spatial map of a familiar environment is not affected by a recent fear memory experience.
2. A recent fear memory experience primes the network for the formation of an accurate map of a novel, unfamiliar environment upon minimal exposure.
3. The map of the familiar and novel environment end the same after familiarization.
### Questions
1. Is the neural network/manifold the same in the Familiar Box after a Shock?
2. Is the neural network/manifold the similar in the Novel Box as in the Familiar Box?
3. Did the process for encoding changed? --> Connection to Morphing Box Experiment
	1. Why is the Novel Box better encoded after shock? 
		1. Linear to exponential encoding?

### Experiment Information
#### Comparing sessions:  
- Spatial map formation in naive animals: FS1 vs FS9
- Stability of a familiar spatial map in naive animals: FS7 vs FS8 vs FS9
- Effect experience on a familiar spatial map: FS9 vs FS10/FS11/FS12
- Effect experience on spatial map formation: FS1 vs NS1
- Effect experience on the stability of a spatial map: NS7 vs NS8 vs NS9 (and then compare to FS7 vs FS8 vs FS9)
#### cFC animals
- 7021: all sessions (caution: animal explored little in sessions FS12, FS16, FS18)
- 7050: all sessions (caution: imaging FOV was out of focus during session NS3)
- 7369: only use sessions FS7 till FS12 to look at the effect of experience on a familiar map
- 7416: all sessions
- 7417: all sessions (caution: session NS8 is missing due to recording error)
- 7513: all sessions
- 18116: all sessions
- 18154: all sessions (caution: focus of miniscope shifted during session NS3)
- 20762: only use sessions FS1 till FS9 to look at spatial map formation in naïve animals as the mouse didn't learn

#### NS control animals
- 14515: all sessions
- 15128: all sessions
- 16562: all sessions (caution: animal explored little in session FS2 and imaging FOV was out of focus in FS14, NS4, NS5)
- 16584: all sessions (caution: animal explored little in session FS16)
- 18115: all sessions
- 20765: all sessions
### Tasks
- [ ] Nathalies Paper (code need to run starting on March) - 
	- [ ] Open Field Dynamics
		- [ ] Dimensionality reduction on Bins
			- [ ] Correlated in time? → Do they cluster correctly?
			- [ ] Diversity between days? → Do they cluster correctly?
				- [ ] Create subsampling of neurons?
		- [ ] Implement
			- [ ] Random control for Decoding
				- [ ] Open Field Dynamics
				- [ ] For morphing Box
			- [x] Structural index 
				- [ ] Add RAW Binarized and Fluoresence to FS1 and FS9
				- [ ] For Full Dataset
					- is hinting, that the raw data has structure based on entropy
			- [ ] Entropy Learning measure 
				- [x] low dim space
				- [x] high dim space to ensure cebra is doing correct
				- [ ] Adapted to 
					- [ ] within Animal Tasks
					- [ ] Control to Conditioned
				- [ ] Random Control
			- [ ] [Shape similarity](https://www.biorxiv.org/content/10.1101/2025.01.10.632411v1.full.pdf)
			- [ ] Determine Neuron importants
				- [ ] Open Neural Network and look inside 
		- [ ] Create for all 
			- [ ] Cells
				- [ ] Structural Indices
				- [ ] Feature (Location) Entropy Measure
				- [ ] Shape Similarities
					- [ ] do they cluster?
			- [ ] Subsampled Cells
				- [ ] Place Cells
				- [ ] Non-Place Cells
- [ ] Own questions
	- [ ] Model Adaptation
	     - Is it possible to extract cells that are equally meaningfull?
	- [ ] Multi-Dataset
		- How can multi dataset training be usefull?
		- How does it work internally?
- [ ] Model Adaptation
	- [ ] Is it possible to extract cells that are equally meaningfull?
- [ ] Multi-Dataset
	- [ ] How can multi dataset training be usefull?
	- [ ] How does it work internally?
---
- [ ] 
- [ ] Learning Evaluation 
	- [ ] Low dim space (entropy)
	- [ ] High dim space (cosine similarity spread?)
		- [ ] Is the cosine similarity mean calculated as the mean of all cosine similarity values between all vector pairs?
- [ ] How much Structure Index (low and high dimension in global and local) is present in
	*Structural index is hinting, that the raw data has structure based on entropy*
	- [ ] Novel Box 1. day 
	- [ ] Novel Box 1. day after fear conditioning
- [ ]  How much [Shape similarity](https://www.biorxiv.org/content/10.1101/2025.01.10.632411v1.full.pdf)) is present in
	- [ ] Novel Box 1. day 
	- [ ] Novel Box 1. day after fear conditioning
- [ ] What about decoding accuracy?
	- [ ] Is a specific model better in decoding any location if it is trained on a specific dataset and tested on any other dataset?
- [ ] Evaluate Learning Measure in Locations?

### Intrinsic Imaging + Morhping Box
- [ ] Test [MARBLE](https://www.nature.com/articles/s41592-024-02582-2#Fig5)
	- [ ] on morphing box experiments (Data Driven)
		- [ ] to check if manifold representations are significantly different between box locations
	- [ ] Intrinsic Imaging
		- [ ] stationary
		- [ ] mobility

### Detect sell assemblies using 
- [ ] What type of cell are detected?
	- [ ] CEBRA (opening up neural network)
	- [ ] Unsupervised:
		- [ ] [PGAM](https://github.com/BalzaniEdoardo/PGAM)
		- [ ] [MARBLE](https://www.nature.com/articles/s41592-024-02582-2#Fig5) ?

Starting from here less important than Morphing Box
______________________________________________________________________
- [ ] Learning Measurements
	- [x]  Decoding
		- [x] Absolute
	- [ ] Distribution inside Similarity Measure
		- [x] Create artificial place cells based on bin (to create comparable datasets)
		- [x] Calculate Spatial Information of bin (Mutual Information)
			- [x]  Intuition: Spikiness difference of a bin in different conditions
		- [ ] Intuitive Method (Overlap)
			- [x] Remove Outlier (based on denstity)
			- [ ] Cut 3D surface into 2D
				- [x] PCA
				- [ ] Shifted Polarcoordinates
			- [x] measure overlap
				- [x] Normalize Distribution Samples
				- [x] Create KDE
				- [x] calc KDE overlap
		- [x] Komogorov-Smirnof
		- [ ] Information Content (inside similarity)
			- [ ] move code of information_content function to similarity calculation function
			- [ ] compare RAW and Embedding Distribution Learning Measure
				- [ ] Similarities of RAW Data resemble 
					- [ ] embedding?
					- [ ] (only implement normal entropy)
					- [ ] kde_entropy?
			- [ ] Does Entropy et. al compare to decoding accuracy?
				- [ ] Map continuouse position decoding to bins
				- [ ] compare plot of subplots to each other
		- [ ] Cross-Entropy
	- [x] Number for learning
		- [x] Soingle bin learning
			- [x] Entropy
				- [x] Remove Outlier (based on denstity)
				- [x] create KDE (bootstrapping)
				- [x] Calculate Entropy 
					- [x] **Normalize** by 1. maximum entropy 2. occupancy
		- [ ] Full Dataset Learning
			- [ ] Mean Entropy number
			- [ ] Test: Different Iterations create different values?
				- [ ] NS1 should be lower than FS1
- [ ] Check speed representations are not the reason for more similar bins
	- [ ] Filter for speed ranges between 2 and 5 ? 
	- [ ] create similar entropy values as before
- [ ] Test general Dataset models based on adaptation
	- [ ] check if coloring is correct
	- [ ] create models
		- [x] normal
		- [ ] random
		- [x] adapted (to all datasets)
			- [x] normal
			- [ ] random
	- [ ] Plot Embeddings 
		- [ ] check if some look really bad
	- [x] Adapt Model to other Inputs (different Datasets)
	- [x] Decoding
		- [x] Original Model Dataset ("own" test data)
		- [x] Adapted Model to all other test datasets
	- [x] Plot Barplos for all decodings
	- [ ] Determine neurons responsible for position decoding
- [ ] Create Muli-Animal model (1 model per dataset, pos-/neg examples from all)
	- [ ] Get more Data from Nathalie
	- [ ] Global model (distinguish environment you are in)
	- [ ] First time in Environment model for determining precision of created map
	- [ ]  Determine neurons responsible for position decoding
- [ ] Place Cells
	- [ ]  Opexebo (inscopix) gold standard method
		- [ ] Plot place fields
	- [ ] [[CEBRA]] 
		- [x] Train model for position
		- [ ] Determine Cell influence to position determination in embedding space
			- [ ] test svd on centered positions in cebras embedding 
				- [ ] to get salience and compare with distance as salience (get feeling for significant salience)
			- [ ] reverse_ingeniering_of_cell contributions_to_detect_cells that_are_similar important_for_pos decoding
		- [ ] For all positions 
			- [ ] Check influence of cells to classification
			- [ ] determine place cells
	- [ ] Compare Opexebo and Cebra Place Cells
	- [ ] Check results on subset of neurons
		- [ ] Create Cebra model on 
			- [ ] only place cells
			- [ ] all others
		- [ ] check decoding
		- [ ] plot comparing both
	- [ ] Implement stopping at specific loss and check 
		- [ ] Check results on subset of neurons
			- [ ] Create Cebra model on 
				- [ ] only place cells
				- [ ] all others
			- [ ] check decoding
			- [ ] plot comparing both
- [ ] Learning Measurements for other features (corner? grooming?)
	- [ ]  Decoding
		- [ ] Binned data
			- [ ] Create a Cutoff, of minimum number of datapoints needed in training data for predicting. Do not try to predicting labels, where a true label of a bin has a low number of examples in the dataset
			- [ ] How would results look like from a randome model?
			- [ ] ROC: Try creating a perfect model by filtering only specific frames where the perceived corner is unspecific (This is not possible to solve currently, if ever)
## Morphing Box
### Questions 
1. Did a shock changed the process of encoding? --> Connection to Open Field Dynamics
	1. Why is the Novel Box better encoded after shock? 
		1. Linear to exponential encoding?
### Tasks 
- [ ] 
- [ ] Structural 
	- [ ] Adaptation in boxes? How much structure is present?
Starting from here less important than Intrinsic Imaging
______________________________________________________________________
- [ ] Cebra Adapting: Check representation quality between environments (position decoding)
	- [ ] For every environment 
		- [ ] Train model based on 
			- [x] absolute positions
			- [x] relative positions (linear reshaping)
			- [ ] shuffled data
		- [ ] For all Environments
			- [ ] Determine Decoding accuracy for
				- [x] absolute position
				- [x] relative positions (linear reshaping)
			- [ ] Ensure correctness 
				- [ ] 2D Track: Animation of mouse running in 2d space vs predicted position
	- [ ] Create Plot comparing 
		- [ ] cebra embeddings
		- [ ] decoding accuracies
			- [x] absolute positions
			- [ ] relative positions 
	- [ ] Learning Measure (For all Shapes)
		- [ ] Embedding
			- [ ] Entropy (move code so neural.similarity)
			- [ ] Smirnov-Komoglorov
			- [ ] Mahalanobis
		- [ ] RAW Data
			- [ ] Mahalanobis
			- [ ] Smirnov-Komoglorov
			- [ ] https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1011768
- [ ] Implement [structure_index_demo.ipynb - Colab](https://colab.research.google.com/github/PridaLab/structure_index/blob/main/demos/structure_index_demo.ipynb#scrollTo=H1lmPaC3UCXC) Calculation ([paper]([Quantifying the distribution of feature values over data represented in arbitrary dimensional spaces | PLOS Computational Biology](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1011768#pcbi.1011768.s001)))
	- [x] Test on Embedded data
	- [x] Test on RAW data
- [ ] Cell activity determination
	- [ ] Determine neurons responsible for position decoding
	- [ ] Compare with Place Cells determined with skaggs (opexebo)
	- [ ] mutual information [A universal hippocampal memory code across animals and environments | bioRxiv](https://www.biorxiv.org/content/10.1101/2024.10.24.620127v4.full)
- [ ] Automated Detection of corners (Local "cues" (corner, border, center))
	- [ ] If working: Is a save spot represented as a location?
- [ ] Create Muli-Animal model
	- [ ] how do the manifolds look like?
		- [ ] 
	- [ ] Get more Data from Nathalie
	- [ ] Global model (distinguish environment you are in)
	- [ ] First time in Environment model for determining precision of created map
## Rigid Plastic
- [ ] Fix track naming heterogenity
	- [ ] Habe ich in der DB "scrambled 1,5,4,2,3,6" und "cued_A', scrambled: 1 6 5 4 2 3" als solche notiert? Dann stimmt das so.   
	- [ ] I.d.R. habe ich nämlich am häufigsten "scrambled 1 6 4 2 3 5" verwendet.  
	- [ ] Alle "blank" belts bestehen aus einem einzigen, langen Segment (d.h. keine kurzen e.g. 30cm-Stücke).
	- [ ] Proposed from me
		- [ ] 100 cm blank:    [1, 1, 1, 1]
		- [ ] 100 cm 4-seg:    [1, 2, 3, 4]
		- [ ] 180 cm blank:    [1, 1, 1, 1, 1, 1]
		- [ ] 180 cm, 6-seg:    [1, 2, 3, 4, 5, 6]
		- [ ] 180 cm, 6-seg (scrambled 1,5,4,2,3,6):    [1, 5, 4, 2, 3, 6]
		- [ ] 180 cm, 6-seg (unscrambled):    [1, 2, 3, 4, 5, 6]
		- [ ] 180 cm, 6-seg (1,5,4,2,3,6):    [1, 5, 4, 2, 3, 6]
		- [ ] 180 cm, 6-seg test landmarks:    [1, 2, 3, 4, 5, 6]
		- [ ] blank:    [1]
		- [ ] scramble: 164235:    [1, 6, 4, 2, 3, 5]
		- [ ] reversed:    [6, 5, 4, 3, 2, 1]
		- [ ] scramble: 154326:    [1, 5, 4, 3, 2, 6]
		- [ ] 180 cm cued:    [1, 2, 3, 4, 5, 6]
		- [ ] wheel:    [1]
		- [ ] 150 cm blank:    [1, 1, 1, 1, 1]
		- [ ] 150 cm, 6-seg:    [1, 2, 3, 4, 5]
		- [ ] 150 cm cued:    [1, 2, 3, 4, 5]
		- [ ] 150 cm cued reversed:    [5, 4, 3, 2, 1]
		- [ ] cued_A:    [1, 2, 3, 4, 5, 6]
		- [ ] cued_A', scrambled: 1 6 5 4 2 3:    [1, 6, 5, 4, 2, 3]
		- [ ] cued_A'', scrambled: 1 4 6 2 3 5:    [1, 4, 6, 2, 3, 5]
- [ ] Creat Yaml Files for all datasets
- [ ] Place Cell/Field Detection
	- [ ] Place Cell
		- [x] Bin Locations
		- [x] normalize by position (amount of time per position)
		- [x] only on moving periods (>2m/s)
		- [x] Calc Spatial Information
		- [x] spike map,  rate map, normalization
		- [ ] Stability criteria
			- [ ] Talk with Marianelli
			- [ ] define minimum number active laps of cell (typically 40%, bad 20-30%, good 50-60%)
			- [ ] activity in odd and even other laps (should be same)
			- [ ] first 1/2 laps, second 1/2 laps (should be same if placefiled had not to be initialized, check rois if not)
			- [ ] first 1/3 laps, second 1/2 laps (should be same if placefiled had not to be initialized, check rois if not)
			- [ ] infield, out offield (noisy? amplitude activity (DFF) or number events(Binarized)) 
		- [ ] Detect Cells with CEBRA
			- [ ] NEED TO BE DEFINED
	- [ ] Detect Place Field
		- [ ] Local Place Fields
			- [ ] get ids of cells with high salience scicore 
			- [ ] create fake neural dataset 
				- [ ] remove cells with low salience from original neural dataset 
			- [ ] Detect best way for place cell detection 
				- [ ] Create synthetic dataset
				- [ ]  look at decoding rate of (decoding should still be possible for stimulus)
					- [ ] stimulus (local or global cues)
					- [ ] position (local or global cues)
					- [ ] distance (distance or time cues)
				- [ ] Compare synthetic datasets place cells with original 
		- [ ] Global Place Fields
			- [ ] get ids of cells with high salience scicore 
			- [ ] create fake neural dataset 
				- [ ] remove cells with low salience in all 3 belts (some cells should match)
			- [ ] look at decoding rate of (decoding should still be possible for stimulus)
				- [ ] stimulus (local cues) --> no activity in Blank belts 
				- [ ] position (global cues)
				- [ ] distance (distance or time cues)
	- [ ] Compare with Lorenzos Dataset: `X:\Users\LorenzoMar\VR\DON-019887\20240306`
	- [ ] create circular plot for place cell remapping
	- [ ] Check if Decision Tree can be used for cell/field detection
- [ ] Renans environment cell correlation for detecting cofirering of cells à may local cue cells?
- [ ] Test Multi-Animal/Session
	- [ ] What is possible with the embedding created by cebra for Multi-Animal?
	- [ ] How does the Model work?
	- [ ] Create similarity Measure
	- [ ] 
- [ ] Ensure correctness 
	- [ ] 1D Track: Y-axis decoded position, X-axis real position. Background filled with cells sorted by activity
## Intrinsic Imaging
- [ ] Plot number active cells 
	- [ ] Determine firering by chance and (red line)
	- [ ] check at population activity histogram 
- [ ] **Everton needs**: distributions per animal within each age group (as opposed of pooling all the cell activity from all animals in each age group)
- [ ] Create Manifold Space using Procrustes or similar ([Shape similarity](https://www.biorxiv.org/content/10.1101/2025.01.10.632411v1.full.pdf) ) 
	- [ ] Are the Manifold samples grouping by 
		- [ ] age
		- [ ] sex
		- [ ] something else?
- [ ] Check Temperature of systems using Lorenzo Marianellis Monte Carlo method?
- [ ] Flavio said maybe not: Rerun intrinsic imaging pipeline within 
	- [ ] correct fps
	- [ ] correct gcamp settings
		- 0.7 for GCaMP6f
		- 1.0 for GCaMP6m
		- 1.25-1.5 for GCaMP6s


# Read
- [ ] [Neuro-musculoskeletal modeling reveals muscle-level neural dynamics of adaptive learning in sensorimotor cortex | bioRxiv](https://www.biorxiv.org/content/10.1101/2024.09.11.612513v1.full)
- [ ] [Fig. 2: The utility of low-dimensional attractor networks. | Nature Reviews Neuroscience](https://www.nature.com/articles/s41583-022-00642-0/figures/2)
- [ ] Learn about Effective communication ! 
	- [ ] [how_to_make_a_great_presentation](https://www.ted.com/playlists/574/how_to_make_a_great_presentation)
	- [ ] [Best suggestion writing grants](https://corticalia.wordpress.com/2015/09/01/how-to-write-a-winning-grant-proposal/)
	- [ ] [Book: Art of Explanation](https://www.goodreads.com/book/show/64631477-the-art-of-explanation)
	- [ ] [Simplify Complex Ideas](https://www.forbes.com/sites/carminegallo/2023/10/06/4-proven-rules-to-simplify-complex-ideas/)
- [ ] Hopfield Networks 
	- [ ]  [Explaining the Paper: Hopfield Networks is All You Need – Frank's World of Data Science & AI (franksworld.com)](https://www.franksworld.com/2020/08/10/explaining-the-paper-hopfield-networks-is-all-you-need/)
	- [ ] Hopfield nets have a scalar value associated with each state of the network, referred to as the "energy", _E_, of the network, where:
		- 𝐸=−12∑𝑖,𝑗𝑤𝑖𝑗𝑠𝑖𝑠𝑗−∑𝑖𝜃𝑖𝑠𝑖![{\displaystyle E=-{\frac {1}{2}}\sum _{i,j}w_{ij}s_{i}s_{j}-\sum _{i}\theta _{i}s_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/48e21b0de52d461e2fa2bed7c0e4fdcfb5ebfe5c)
		- This quantity is called "energy" because it either decreases or stays the same upon network units being updated. Furthermore, under repeated updating the network will eventually converge to a state which is a [local minimum](https://en.wikipedia.org/wiki/Local_minimum "Local minimum") in the energy function (which is considered to be a [Lyapunov function](https://en.wikipedia.org/wiki/Lyapunov_function "Lyapunov function")).[[7]](https://en.wikipedia.org/wiki/Hopfield_network#cite_note-Hopfield1982-7) Thus, if a state is a local minimum in the energy function it is a stable state for the network. Note that this energy function belongs to a general class of models in [physics](https://en.wikipedia.org/wiki/Physics "Physics") under the name of [Ising models](https://en.wikipedia.org/wiki/Ising_model "Ising model"); these in turn are a special case of [Markov networks](https://en.wikipedia.org/wiki/Markov_networks "Markov networks"), since the associated [probability measure](https://en.wikipedia.org/wiki/Probability_measure "Probability measure"), the [Gibbs measure](https://en.wikipedia.org/wiki/Gibbs_measure "Gibbs measure"), has the [Markov property](https://en.wikipedia.org/wiki/Markov_property "Markov property").
		-  Ulterior models (more capacity + on shot learning)
		- [Engrams: A Window into the Memory Trace | SpringerLink](https://link.springer.com/book/10.1007/978-3-031-62983-9?sap-outbound-id=ECEDD6AC52DBC0B3431FBD677311B581D146F18F#toc)
		- [Lagrangian mechanics - Wikipedia](https://en.wikipedia.org/wiki/Lagrangian_mechanics
- [ ] Cebra Questions
	- [ ] Based on your current knowledge, would cebra be still the way to go for Embedding Neural Data? Why?
	- [ ] How probable is it to have overfitting with the default settings of cebra?
		- [ ] Would you suggest fine tuning of a cebra model for specific goals?
		- [ ] Best way to extract single cell contribution to an embedding?
	- [ ] How are the training examples choosen/created ?
		- [ ] If she wants to have more details about the question:
			- [ ] Are the positive and negative examples for training with contrastive learning based on
			- [ ] the raw population vector ?
			- [ ] a population vector after encoding happened ?
- [ ] This is the paper I mentioned - internally organized neuronal sequences in CA1 when the animal runs on a dark and smooth surface track distance run: 
	- [ ] (https://donatolab.slack.com/archives/D0566KJRN1X/p1711382382238229)
	- [ ] [https://www.sciencedirect.com/science/article/pii/S0896627315008417?via%3Dihub
	- [ ] (https://www.sciencedirect.com/science/article/pii/S0896627315008417?via%3Dihub)
	- [ ] (https://donatolab.slack.com/archives/D0566KJRN1X/p1711382486010519)
	- [ ] And here there is a nice way to detect ensembles (https://donatolab.slack.com/archives/D0566KJRN1X/p1711382486842449) 
	- [ ] https://www.nature.com/articles/s41593-021-00804-w#Sec2 
	- [ ] and maybe something useful here too:  (https://www.nature.com/articles/s41467-022-30198-7?fromPaywallRec=false)
- [ ] LLM Methods for similar Tasks like CEBRA? (SciCore provides LLMs)
- [ ] BraiAN: 
	- [ ] paper: https://pubmed.ncbi.nlm.nih.gov/23300432/, 
	- [ ] [Ch3fUlrich/BraiAn: copy of BraiAn + own eddits (github.com)](https://github.com/Ch3fUlrich/BraiAn)

# Code Improve
## Fix
- [ ] Create bin evaluation method
	- [ ] Entropy
		- [ ] check why Entropy is at a specific location super low, **0 Entropy** should be changed to None
		- [ ] **Normalize** 
			- [ ] Entropy by maximum entropy to have comparable numbers
- [ ] Plot of Subplots for 2D (evaluation of distribution quality "learned feature")
	- [ ] put reference bin in the center to make it more comparable in between bins (all look similar)
	- [ ] Recreate Plots for
		- [ ] Entropy
- [ ] Cross - Entorpy
	- [ ] Rerun with fixed Plot of subplots for 2D
	- [ ] check how it is comparing with Entropy
- [ ] Controlls for PCA works 
	- [ ] move center to center of cut open Sphere 
		- [ ] Sphere to Plane polar coordinate calculation for individual point distributions 
		- [ ] Change scaling in subplots of 2d representation of point distributions 
- [ ] KDE on RAW data? 
	- [ ] how is the KDE working in high dimensional data?
	- [ ] bootstraping? 
	- [ ] unnatural data?
- [ ] Add Stopping at reaching a learning plateau to create better comparable 
	- [ ] **WARNING**: This can not be used for comparing distributions between models, since model will get more precise in position definition of samples in embeddings space
## Speed 
- [ ] 
## Nice to have
- [ ] change datasaving to .npz files and save different versions of a datatype in it (raw, cleaned, binned)
- [ ] change Cebras class and CebraOwn to make it work when CebraOwn also inherits from Model
- [ ] .toml and tests for continuose integration (pypi) also license needs to be defined
- [ ] Create a own class as a CEBRA wrapper and integrate functions inside this class
- [ ] Proper template class for CAM structure analysis 
	- [ ] Create a new way to work with cam data (look todo inside REAMDE.md)
	- [ ] completely restructure code:
		- [ ] label behavior type (e.g. position, stimulus, usw.)
			- [ ] add source of information e.g. inscopix, cam 
		- [ ] probably integrate cam metadata inside the cam
		- [ ] inside cam there should be also a preprocessing and processing class 
			- [ ] processing should be some kind of model like sleap or deeblabcut 
			- [ ] processing should not be automatically done
- [ ] Correlation, STTC
- [ ] Spectral Analysis on binarized data
	- [ ] Power spectra for module definition of gridcells 
- [ ] Manifold models 
	- [ ] UMAP, ISOMAP 
- [ ] build Graphs based on connections (from correlation or similar)
	- [ ] Degree 
	- [ ] transitivity 
	- [ ] fragmentation 
	- [ ] consistency / link predictability distribution 
- [ ] BINARY to video converter (for renan and others)
- [ ] add filter for cells+frames into dataset class
- [ ] Analysis 
	- [ ] Correlation + Plots
	- [ ] Cell Contour determination + Plots (cabincorr)
	- [ ] Cell deduplication from Animal class
	- [ ] STTC + Plots
	- [ ] Graph 
		- [ ] Density, Transitivity, avg cluster coeff, avg shortest path, radius, diameter, median page rank