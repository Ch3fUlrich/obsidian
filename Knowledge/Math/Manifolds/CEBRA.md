Consistent EmBeddings of high-dimensional Recordings using Auxiliary variables

# Summary

## Goal
- Uncover Neural Dynamics
    - Superviced and Unsupervised
    - across tasks (sensory and motor)
    - across species
- Mapping of space
    - uncover complex kinematic features
    - consistens latent spaces

## Implementation
1. #TODO 
2. Network Architecture (default)
		model_architecture: str = "offset1-model",
		device: str = "cuda_if_available",
		criterion: str = "infonce",
		distance: str = "cosine",
		conditional: str = None,
		temperature: float = 1.0,
		temperature_mode: Literal["constant", "auto"] = "constant",
		min_temperature: Optional[float] = 0.1,
		time_offsets: int = 1,
		delta: float = None,
		max_iterations: int = 10000,
		max_adapt_iterations: int = 500,
		batch_size: int = None,
		learning_rate: float = 3e-4,
		optimizer: str = "adam",
		output_dimension: int = 8,
		verbose: bool = False,
		num_hidden_units: int = 32,
		pad_before_transform: bool = True,
		hybrid: bool = False,
1. Learning Method 
	1. Contrastive Learning

### Demo Notebook
[Encoding of space, hippocampus (CA1) — cebra 0.3.1rc1 documentation](https://cebra.ai/docs/demo_notebooks/Demo_hippocampus.html)
More specifically, this is a mega-notebook, containing all the informations presented in [Hypothesis-driven analysis](https://cebra.ai/docs/demo_notebooks/Demo_hypothesis_testing.html), [Consistency](https://cebra.ai/docs/demo_notebooks/Demo_consistency.html), [Decoding](https://cebra.ai/docs/demo_notebooks/Demo_decoding.html) and [Topological data analysis](https://cebra.ai/docs/demo_notebooks/Demo_cohomology.html) into a single demo notebook. We recommand that you go through those individual notebooks instead, as they present some of the most recently implemented helper functions for plotting, saving models, etc.
## Data
- 2P or Neuropixels
    - Behaviour
	- Neural
## CEBRA-Components

### CEBRA-Time
### CEBRA-Behavior
### CEBRA-Hybrid

# Paper 
## Abstract
Mapping behavioural actions to neural activity is a fundamental goal of neuroscience. As our ability to record large neural and behavioural data increases, there is growing interest in modelling neural dynamics during adaptive behaviours to probe neural representations[1](https://www.nature.com/articles/s41586-023-06031-6#ref-CR1 "Urai, A. E., Doiron, B., Leifer, A. M. & Churchland, A. K. Large-scale neural recordings call for new insights to link brain and behavior. Nat. Neurosci. 25, 11–19 (2021)."),[2](https://www.nature.com/articles/s41586-023-06031-6#ref-CR2 "Krakauer, J. W., Ghazanfar, A. A., Gomez-Marin, A., MacIver, M. A. & Poeppel, D. Neuroscience needs behavior: correcting a reductionist bias. Neuron 93, 480–490 (2017)."),[3](https://www.nature.com/articles/s41586-023-06031-6#ref-CR3 "Jazayeri, M. & Ostojic, S. Interpreting neural computations by examining intrinsic and embedding dimensionality of neural activity. Curr. Opin. Neurobiol. 70, 113–120 (2021)."). In particular, although neural latent embeddings can reveal underlying correlates of behaviour, we lack nonlinear techniques that can explicitly and flexibly leverage joint behaviour and neural data to uncover neural dynamics[3](https://www.nature.com/articles/s41586-023-06031-6#ref-CR3 "Jazayeri, M. & Ostojic, S. Interpreting neural computations by examining intrinsic and embedding dimensionality of neural activity. Curr. Opin. Neurobiol. 70, 113–120 (2021)."),[4](https://www.nature.com/articles/s41586-023-06031-6#ref-CR4 "Humphries, M. D. Strong and weak principles of neural dimension reduction. Neuron. Behav. Data Anal. Theory 
https://nbdt.scholasticahq.com/article/24619
(2020)."),[5](https://www.nature.com/articles/s41586-023-06031-6#ref-CR5 "Zhou, D., & Wei, X. Learning identifiable and interpretable latent models of high-dimensional neural activity using pi-VAE. Adv. Neural Inf. Process. Syst. 
https://proceedings.neurips.cc//paper/2020/file/510f2318f324cf07fce24c3a4b89c771-Paper.pdf
(2020)."). Here, we fill this gap with a new encoding method, CEBRA, that jointly uses behavioural and neural data in a (supervised) hypothesis- or (self-supervised) discovery-driven manner to produce both consistent and high-performance latent spaces. We show that consistency can be used as a metric for uncovering meaningful differences, and the inferred latents can be used for decoding. We validate its accuracy and demonstrate our tool’s utility for both calcium and electrophysiology datasets, across sensory and motor tasks and in simple or complex behaviours across species. It allows leverage of single- and multi-session datasets for hypothesis testing or can be used label free. Lastly, we show that CEBRA can be used for the mapping of space, uncovering complex kinematic features, for the production of consistent latent spaces across two-photon and Neuropixels data, and can provide rapid, high-accuracy decoding of natural videos from visual cortex.