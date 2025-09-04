https://www.nature.com/articles/s41586-024-08397-7
# Abstract
## hippocampus correlated variables
- space
- time
- sensory cues
- rewards
- actions

## Results
Hippocampal firing is influenced by
1. External variables (limited)
2. online action plans
3. goal uncertainty

# Main
- High processed sensory inf. -> Hippocampus -> Space and time
- Hippocampus = Top-Down Effector sys involved in planning and initiating voluntary actions
- Sustain working [[Memory Improvement]] 
# Tasks
### Mouse-controlled auditory navigation task
- Probe trials with frequencies hinting on reward port location. 
- Truncated at different frequencies

### Non-spatial and spatial cell assemblies
- CA1 pyramidal cells detecting frequency space
- Cells are Theta-phase precession and theta compression
- tone cells 1,129
	- many had low firing rates
	- 50% had place field 
	- firing driven my approach of port chosen by mouse
		- displaying tone (left), 
		- mixed (middle) and 
		- place (right) tuning
- 60% Cells co-modulated to 
	- Place 
	- Tone

### Population activity and behavioural goals
- 100ms activity bins
- UMAP
- 

### Data (CA1)
- 235 Neurons per session 
	- 37 sessions
	- 6 mice
		- 83-372 cells
		- 8113 in total
		- 6220 pyramidal cells
		- 1893 putative interneurons
- 128 site double sided silicon probes

# Methods

## Movement trajectory clustering ( Agglomerative hierarchical clustering)
- split into 7 parts (1 part to every pole)
- Complete Linkage -> less clusters
- different movement trajectories lead to different firing patterns within same task conditions
- Remapping happens even with same trajectory if task changed -> task engagement

## Poisson generalized additive model (P-GAM)
- log(λ) = β_ChoiceLick * f_ChoiceLick(t) + β_NoTonePort6 * f_NoTonePort6(t) + β_Spontaneous * f_Spontaneous(t) + ...
- Non-Linear mapping between
	- spike counts
	- cont. vars
		- position 
			- forward 
				- No-tone (for place cells)
				- Tone (change of place cell activity)
			- backward
				- all trials (consistent activity)
		- progression to port, normalized to 120cm (neuron firing related to location or tone?)
	- discrete events
		- first Licking of port, timestamps (effect of licking)
			- choice licks
			- no-tone port 6 licks (specific location activity)
			- spontaneous forward and return licks (exploration?)
			- home licks (start activity)
		

## Cell assembly determination
1. Spike Train Binning
2. Firing Correlation Matric
3. PCA
4. Random firing correlation threshold
5. ICA (for independence)