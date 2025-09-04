## 2025

### 8
#### 25-29
- Structure index
	- add significants calculation using mixedLinarModel to plot_df_group_values
	- Use nathalies comparisson methods for SI values, what values are also available? ANOVA test?
	- unbiased comparisson from pooling all animals together for significants between tasks
#### 18-20
- Structure Index
	- The difference between groups over time changes
- Shape similarity
	- sample flow from same reference point (0,0)
#### 11-15
- Switcht to Windows 11 
	- setup everything and created proper req.yml
- Shape Similarity
	- Plots
		- samples flow
		- self referenced (animal wise start position is 0,0)
			- center_flow
			- sample flow
#### 01-06
- Checked if box rotation is working properly
- Shape Similarity
	- Plots
		- Heatmap
			- added colorbar numbers
		- scatter
			- add centroids 
				- and  spread as shaded area
				- and flow
	- saving
		- solve recomputing problem 
		- added backup saving before complete
	- rerun with soft-matching on 
		- binarized data
		- fluoresence data
	- Embedding
		- MDS
			- Does not look great
		- MDS+PCA

### 7
#### 28-31
- Shape Similarity
	- Replicated results form [Quantifying Differences in Neural Population Activity With Shape Metrics](https://www.biorxiv.org/content/10.1101/2025.01.10.632411v1.full) which is based on data from 
		- [Local origin of excitatory–inhibitory tuning equivalence in a cortical network](https://www.nature.com/articles/s41593-024-01588-5) 
#### 21-26
- B&A Club meeting
- Strukture Index
	-  Pool Animals from cFC and NS for FS1-FS9 and calculate significants between those days
	- check if SI is increasing over experience. AUC continuously increase? line plot
- Shape similarity
	- improved filtering of data
	- 
#### 14-18
- fixed outside box positional errors that were introduced because of smoothing
- added automated rotation of position data if cue card location is present
- Shape Similarity
	- Cell Tuning definition
		- added rate map for 2D environments
			- tested output on pca result
			-  IMPROVE PLOTTING OF 3D pca components of rate maps
	- Recomputed
		- using tuning maps (flattened 2D maps) to check if results are better
	- create color gradient for conditons and better plotting
#### 7-11
- Structural Index
	- added pvalue correction to function
	- Rerun with more Bins (looks like more robust values)
		- Moving
		- Stationary

- Shape Similarity
	- Journal Club
	- Recomputed Shape Similarity on full dataset with same # of neurons
	- Visualization  like in the methods of the [paper](https://www.biorxiv.org/content/10.1101/2025.01.10.632411v1.full)
		- 20 Dim. MDS (they had 3.4% distortion)
		- 2D PCA (85% variance explained)
		- Use a hierarchical sorting (ward) Dendogram on Distance Heatmap and reorder
	- started working on 2D place cell detection, since this is needed for proper cell tuning detection and afterwards shape similarity calculation. Tuning of cells is needed. !!!!!
#### 1-4
- Structure Index
	- Added significance plotting between Experimental and Control
		- Mann-Whitney U test
		- add a marker for significance
	- Added significance plotting between inside groups
		- Wilcoxon signed-rank test
			- for local, mid and global structural Index values
			- AUC
			- power function parameters
				- slope
				- intercept
				- exponent
		- created a lower triangle plot  
	- Rerun stationary with 1 shuffle
- Shape Similarity
	- Recompute with same # of neurons

### 6
#### 26-30
- Organized Computer updates + updated workstation
- Structure Index
	- added unparametric statistical test and plot for comparing cFC and control group
		- -> no statistical difference between cFC and control
	- Rerun with velocity cap of 35cm/s --> less noise ?
#### 23-25
- added data_filtering information to 
	- data plotting
	- model name
	- structural index name (since model name)
- fixed saving issues of cebra
- fixed velocity values 
- Structural Index
	- All Structural indices are significant for the moving frames (based on shuffles)
	- create velocity plots to compare to decide for speed
	- cap mouse speed and rerun structure index
#### 17-20
- improved structure index calculation speed that was accepted
- added capability of filtering data by range defined initially + plotting
- added data_filtering by range. proper naming and times still need to be defined
- added positional data cleanup using 1% high freqency noise filtering 
#### 10-13
- Created proper visualization of speeds using using different filtering and merging methods to search for a proper cut
- signal processing 
	- tested different noise reduction methods used by anja and mauro. 
	- found proper method based on removing 1% noise detected by fast fourier transformation and power spectral embedding instead of fixed 2Hz setting
#### 02-06
- Shape Similarity
	- Run calculations
	- improved coloring and plotting
	- added specific coloring and plotting for nathalies stuff
- Structural Index
	- fixed issue with k beeing too high for low number of smaples points in cloud
	- rerun on stationary data to look into results
	- 
### 5
#### 26
- improved automated plotting of structural index
#### 19-25
- Version control B&A
- fixed moving detection bug
- fixed some small bugs 
- rerunning for moving and stationary
	- model creation
	- feature similarity
	- structural index
	- 
### 4
#### 25-28
- Shape Similarity
	- Create Shape Similarities between all manifolds
	- create manifold spaces using different simple embedding methods
	- Procrustes distance explanation
- Decodings
	- Create Session.task_cross_decoding function based on animal.session_Cross_Decoding function
	- random model
		- updated code so random model is based on reference model. Update plots 
#### 24
- feature similarity:
	- fixed mahalanobis for inside similarity
- SI
	- finish up automated structural index dictionary creation based on criteria
	- create general plot for SI function based on average of all animals of a specific condition

#### 23
- integrated into mother class
	- Learning Measure
		- density plots 
		- kde_entropy for information content determination
		- add standard deviation to inside similarity calculation and plot to ensure that mean is a proper description on the population vectors
- rerunning inside similarty calculations
#### 22
- integreate structural index summary plots into mother class
#### 17
- add loading to mother
- add information extraction from animals to mother
#### 14-16
- running feature learinig
	- cosine similarity inside and between groups
- created proper plotting functions for structural index
- create cebra models for all datasets
	- create plots based on cebra models
#### 10
- improved SI code
- improved plotting for feature labels in 2d using numba MDS 
- generated data for SI
- started working on general learning measure evaluation analysis
#### 9
- test decoding function with new npio saving function
- SI ready to be used
#### 8
- add plots for single task decodings to cross decoding function
- Added saving of adapted models and decoding statistics
- fixed issue with wrong task id in metadata
#### 4-7
- Openfielddynamics: 
	- restructured + created yaml files
	- converted raw data to useable data
	- started creating cebra models
#### 2-3
- send doc agreement to university
- pushed proper decoding function
- created powerpoint for flavio
#### 1
- fixed decoding perfomance bug (too good to be true error)
### 3
#### 24-28
- Automated n-neighbors number determination based on k-cross fold validation
- working on proper model_cross_decoding function
#### 10-22
- Fixed some small issues (helped renan)
- working on stable Structural Index 
### 2
#### 24
	- RUN CODE ON FOR EVERTON ON SCICORE
		- CLONE ANIMAL CLASS AND MANIFOLDS CLASS
		- TEST RUN SCICORE/OTHER/POPULATION_ACTICITY.PY
		- CREATE FILE WITH ALL USEFULL SESSIONS AND RUN ALL
#### 20-21
- created PCA plot for # of component determination
- created population activity analysis code for everton
#### 19
- initial tests with procrustes distance
#### 18
- Read about MARBLE high dim to low dim method (uses Local flow field in highdim space and contrastive learning)
- Preparing for Journal Club about [Hippocampal neuronal activity is aligned with action plans](https://www.nature.com/articles/s41586-024-08397-7#Fig17)
#### 11-14
- provided proper code to nathalie for movement, stationary detection
- [x] Intrinsic Imaging project
    - [x] Write done every steps
        - [x] of Intrinsic imaging pipeline
        - [x] of data that was sent to other people
            - [x] everton
            - [x] cecillia
            - [x] rodrigo
- from bench to bedside
### 1
#### 27-07.02
- Blockkurs How to be a Scientist
#### 24
- Extracting information for Everton
	- Precise Graph properties
	- Significant
- Extracting firing rates and coactivity information for moving, stationary
#### 20-23
- working on Clean Notebook for Nathalies Paper
#### 13-15
- Looked into [Quantifying Differences in Neural Population Activity With Shape Metrics](https://www.biorxiv.org/content/10.1101/2025.01.10.632411v1.full.pdf)
## 2024

### 12
#### 16
- Initial tests using Structural Index from de la prida
#### 9-12
- Journal Club + Implementation of Method from DeLa Prida
- Prepare for exams
- Wrote a better (not perfect) wrapper of cebra to be able to add functions to the model itself
#### 2-6
- Improve repository skills (Lecture Programming)
- High Performance Computing Workshop
- talked with everton. He currently does not need data but had to do other stuff first.
### 11
#### 18-28
- fixed color issue of multi-session embedding plots
- Created Ansible script for automated installation of software on Windows
- Cage change
- Worked on helper notebook for showing off functions
#### 11-15
- Helped Renan, Nathalie
- created PR
- create proper todo list
-  test accuracy of all models against all other models (it is expected, that remapping happens)
#### 8
- ASK FLAVIO: 
	- Nathalies Box shapes: 
		- Is it correct, that place cell remaps based on positioning of the cue and size of the environment, without changing the relationship or location of the placecell peak?
		- Decoding accuracy between environments
			- relative position measurement to box location --> 
				- checks for place cell reshaping
				- This should work in theory for square box shapes, but what about different box shapes?
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
#### 4-7
- Mouse in a Box 
	- create tasks with box information
		- plot locations and neural data
### 10
#### 29
- fixed pc-specialist computer, added more storage and ram
- started working on appraisal
#### 22-25
- wanted to modified cam class for better automation 
- ASK FLAVIO to take time for changing the code when cam data analysis need to be integrated!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
#### 16
- working on mouse in a box data for nathalie 
	-  Split traces into task specific traces
		- split() created but not optimized
#### 15
- catalins repository setup for publishing packages on pypi
#### 09
- run multiple box bin sizes and create all kind of similarity plots 
#### 03
- parallelized similarity calculations using numba
#### 02
- lecture 
- working on different sized bins for nathalies mouse in a box
#### 01
- reading into connection of entropy, hoppfield and neural networks
- lecture

### 09
#### 30
- worked on lectures
#### 26
- cleanup code
#### 24+25
- Meetings, Lectures
#### 16-20
- Lectures
#### 12-13
- Working on presentation for explaining overlap calculation
#### 11
- created code for Nathalie for splitting up data
#### 04-09
- Created overlap calculation for KDEs so distributions can be compared
- checking soundness of method + powerpoint
#### 03-06
- Implemented Density Calculation using neighbors in 3d space (similar to calculating number of active frames of a cell in a bin for place field determination)
- defining place field by looking at maximum density of distribution and cutoff at 20% of density
- working on powerpoint
#### 02
- finished similarities for raw data + powerpoint
### 08
#### 29-30
- Adapt model trial
	- tested decoding + plot
- Run similarity measures on RAW population activity and create a plot of subplots to see structure
	- fixed mahalanobis distance calculation error
#### 19-28
- Multi-Session Alingment + Plotting embedding space
#### 12
- created 5 cm bin training, test data occupancy plot
- working on outlier removage, waiting for flavios answer
#### 09
- created different plot for accuracy visualization
- working on powerpoint
#### 08
- fixed bug in binning (not creating wrong results before) 
- tried 10cm bins
#### 07
- fixed issue with python environment
- setup home working
- looked into KAN paper
#### 06
- RigidPlastic started working on created yaml files, asked steffen for more detailes
#### 05
- Planed Lectures
- Intrinsic Imaging: improved yaml creator editability
### 07

#### 31
- Intrinsic Imaging:
	- improved plots for activity and coactivity and provided data to everton
#### 30
- Intrinsic Imaging:
	- Analysed firing rates and cofiering counts
#### 28-29
- CEBRA: working on 5% decoding accuracy issue 
#### 27
- fixing cebra error occured after update (only 1D discrete labels possible)
#### 12-26
- Abstract + Poster
#### 19
- Rerun Spatial zones with only center and border
- Ask Flavio:
	- could be enough to quantify the outliers directly (peakinesss or covariance matrix)
- !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!! Flavio Meeting
#### 17-18
- Signed in to LTK
- Read Paper
	- Decoding:
		- It should be possible to train cebra to create an embedding into other spaces. Why not creating a Decoder for features, like positional bins, spatial zones or other behavior types?
	- Theta:
		- Phase precession:
			- correct, that cells move their activity in the phase (fully)? All cells?
			- If Future and Past location is also encoded, this makes the data "dirty", 
				- Decoder for past, current and future position already done?
		- Could it be possible to define cell types based on cell that tend to decode future or past position?
		- (Should we look into wider and less wide bins, to capture theta phase place cell activation?)
#### 16
- added Decoding for Discrete decoder values and plot
#### 15
- added auto discritization of 2D colors in colormap
#### 09-12
- parallelized outlier removage 4000 -> 5
- added decoder plots
- created similarity function with plotting
#### 08
- working on Animal summary plot for decoding accurycies
#### 05
- Created 2D plot of 3D sphere
- !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!! Flavio Meeting
#### 02-04
- Create plots 
- overlap halculation for 2d
#### 01
- Added variance to some plots made for nathalie
- working on border, corner detection
### 06
#### 21-28
- created similarity plots for distance measures between distributions
- create decoding accuracy for different 
	- sessions
		- iterations
#### 20
- finished data loading + plot creations
#### 19
- meeting with catalin and everton
- working on 2D metadata extraction
#### 18
- working on processing class
#### 17
- finished restructuring code, increased modularity
- added fitting to frame for andres
#### 11
- !! added autodetection of folder structure 
	- Folder Animal Session
	- Folders: Animal Session Task or
#### 10
- fire drill
- Finished Wheel Setup with rotary encoder (for andres (simpler))
- working on Inscopix Class (Nathalie)
#### 09
- improved modularity of Rotary Encoder, Treadmill_Setup, Wheel_Setup
#### 08
- started working on Wheel_Setup with rotary encoder
#### 06
- AKS FLAVIO ABOUT:
	- TIME FOR NATHALIES PROJECT!!!
	- Possibility to infer cingle cell RNA-sequence, also for spatial transcriptomics.

#### 05
- meeting: catalin rodrigo, hopfield networks subsampling
- finished parallelization
- !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!! Flavio Meeting
#### 04
- helped anja
- created movement % plots for intrinsic imaging
- worked on parallelization 
#### 03
- helped anja
- working on parallelization
### 05
#### 17
- created place cell plot
#### 15
- Intrinsic Imaging: generated rasters and traces for animals to check what is happening
- plot cells by cells
#### 14
- created "correct" spatial infroamtion plots
- PR
#### 13
- worked on place cell detection method and PR presentation
#### 07
- added per cell plot to animal class
- improved Task 1, 3
#### 06
- Improved Matlab Exercises
- Block course
### 04
#### 30
- fixed issue with spatial information code
- started testing different calculation methods
- ASK FLAVIO ABOUT DIFFERENT SPATIAL INFORMATION METHODS (read paper?)
#### 26
- worked on other place cell plots
- looked in to opexebo place cell detection
	- rate map calculation
	- working on spatial information determination
- helped renan searching error in bmi code
- ASK FLAVIO ABOUT CELL OVERLAP IN SUITE2P (0.75 standard, rennan 0.25) --> cells active at same time
#### 25
- created place cell code with only moving periods + plots
#### 24
- fixed error in wheel size
- improved duration of task
- added binning so datasets
- set cebra to use binned data
- created new plots based on binned data
#### 23
- small code improvements, moving periods
#### 22
- implemented sclaing: moved distance, to get more detail movement information
#### 19
- cage change with anja
- looked into detail for rodrigos bad datasets and proposed new usefull animals and sessions (396 sessions)
#### 18
- Rodrigo: Looked into not noisy sessions
#### 17
- Rodrigo: Looked into noisy sessions
- Anja DTX
- Tracked mouse movement and quantivied moved distances 
	- solution: interpolate moved distance, to get more detail movement information
#### 16
- people: neva PR, Seminar infection process, meeting rodrigo
- fitted 0 position on track to first lap sync in imaging frame
- helped maria
#### 15
- checked lap sync and position on track
- integrated automatic fps extraction from femtonics
#### 12
- anja help dtx
- fixed errors in position extraction, 
	  improved accuracy in mouse position detection on the track
#### 11
- finished velocity extraction from wheel, decided to use own method since results are not fitting
- started working on other behavior extraction
#### 10
- helped maria
#### 09
- Scicore HPC Best practices
#### 08
- changed setup
#### 05
- worked on catalins create velocirty code
#### 04
- finished steffens movement .mat --> wheely.npy and 2p_galvo_trigger.npy
- working on catalins PlaceCell code
#### 03
- added setups, preprocessing + improved
- started on own .mat to position converter
### 03
#### 28
- working on setup, preprocessing modularity for adding ability to process all data that is possible in this lab
#### 27
- started working on correct folder structure detection 
#### 26
- added ability to convert renans mesc_nameing
#### 25
- fixed error in code, test feature detection method --> bad
- Detected 0 vector (all cells inactive) creates an embedding point on the sphere of the ball
- started cleaning up todo list
#### 22
- test feature detection in latent space with normalized distances
#### 21
- test feature detection in latent space with distances
#### 20
- overview about paper for feature detection in neural networks
- build own idea 
#### 19
- Ask Anja about PR 
- helped lorenzo 
- CEBRA
	- added Example folder, moved some files
	- added some type hints in
#### 18
- Looked into CEBRA Details:
- Created AnimalClass ```Usage_Explain.ipynb``` + explained to Lorenzo
#### 15
- extract results to cecillia folder 
- Make Animalcript + Scicore script available for .raw files
	- DON-019887_20240309_002P-F_1_no_VR_S1
	- DON-019887_20240309_002P-F_2_light_Coridor_S1
	- Image_001_001.raw
- started: annotate mice movies


