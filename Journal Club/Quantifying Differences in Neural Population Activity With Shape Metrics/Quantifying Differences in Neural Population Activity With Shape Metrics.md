## Research Lab
- [The Computational Brain Team](https://computationalbrainteam.com)
The Computational Brain Team is part of the UNICOG laboratory and is affiliated with major neuroscience research centers in Paris, including the Institute for Neuromodulation (INM) and Neurospin. Their focus is on understanding higher-order cognitive functions through computational modeling, bridging scales from molecules to behavior. Their approach integrates experimental neuroscience with advanced mathematical and computational techniques. 

- The team has an extensive publication record in high-impact neuroscience journals such as Nature Neuroscience, Nature Communications, eLife, PLOS Biology, and others, spanning topics from neural coding to psychiatric applications.

- Their publications demonstrate rigorous, mathematically grounded methods, including computational modeling, statistical analysis, and advanced neuroimaging techniques.

- Team members collaborate with leading figures in neuroscience and are involved in interdisciplinary projects, further indicating strong standing in the field


## Background
How to quantify similarity/differences in neural population activity?

### Previouse Work 
Source: [CCN](https://2024.ccneuro.org/k-and-t-quantifying-similarity/)
- Linear predictivity scores
  - Linear Predictivity Scores measure how well one set of neural responses (or features) can be linearly predicted from another. In neuroscience, this often involves fitting a linear model (e.g., regression) from one data matrix to another and assessing the explained variance or correlation. Can distort the shape by stretching or shearing #TODO:
- Canonical Correlations Analysiss (CCA)
- Representaional Similarity Analysis (RSA)
  - Compute pairwise dissimilarity matrices for neural responses across conditions, then correlate these matrices between networks or populations.
  - Equivalent to **Procrustes Shape distance**
    - contrained form of linear predictivity. Transformation must be orthogonal (i.e., only rotation and reflection, not arbitrary linear mappings), which preserves distances and angles, making it more suitable for shape comparison.
#TODO:

### Other Methods
|Method|Explanation|Pros|Cons|Limitations|
|---|---|---|---|---|
|Linear Predictivity Scores|Measures how well one set of neural responses can be linearly predicted from another, often using regression models.|Simple to compute; interpretable; widely used in neuroscience.|Can distort shape by stretching or shearing; sensitive to noise.|Assumes linear relationships; may not capture complex neural dynamics.|
|Canonical Correlation Analysis (CCA)|Finds linear combinations of variables in two datasets that are maximally correlated, often used to compare neural activity patterns across conditions.|Effective for identifying shared variance; captures linear relationships; interpretable.|Assumes linearity; sensitive to outliers; may not capture non-linear relationships.|Limited to linear relationships; may not generalize well to complex neural dynamics.|
|Representational Similarity Analysis (RSA)|Computes pairwise dissimilarity matrices for neural responses across conditions, then correlates these matrices between networks or populations.|Captures complex relationships; interpretable; widely applicable in neuroscience.|Computationally intensive; sensitive to noise; requires careful interpretation.| Assumes representational spaces are comparable; may not capture all aspects of neural dynamics.|
| Hausdorff Distance | Measures the distance between two sets of points by considering the maximum distance from a point in one set to the nearest point in the other set.| Robust to noise; captures worst-case differences; interpretable.|Sensitive to outliers; may not reflect overall shape similarity well.|Limited to point sets; may not capture complex shapes effectively.|
| Kendall Distance | Measures the dissimilarity between two shapes by considering the number of pairwise inversions in their point orderings.|Captures shape differences; interpretable; robust to noise.|Sensitive to point ordering; may not reflect overall shape similarity well.|Limited to ordered point sets; may not capture complex shapes effectively.|
| Level-Set Based Shape Morphing | Uses level-set methods to morph one shape into another, capturing complex deformations.|Captures complex shape changes; robust to noise; interpretable.|Computationally intensive; requires careful parameter tuning.|Limited to shapes that can be morphed; may not capture all aspects of shape similarity.|
| Histogram-Based and Graph-Based Methods | Use histograms or graphs to represent shapes and compute distances based on their distributions or connectivity.|Captures shape distributions; interpretable; robust to noise.|Sensitive to binning or graph structure; may not reflect overall shape similarity well.|Limited to specific shape representations; may not capture complex shapes effectively.|
| hyperalignment | Aligns neural activity patterns across conditions or networks to minimize differences, often using optimization techniques.|Effective for aligning complex patterns; interpretable; widely applicable in neuroscience.|Computationally intensive; sensitive to noise; requires careful parameter tuning.|Assumes patterns can be aligned; may not capture all aspects of neural dynamics.|
#TODO: check this table and understand the differences

### Artificial Neural Network methods
- RSA
- linear regression mapppings
  - Find the best linear transformation that maps one activity matrix to another, then measure the correlation between the mapped and original data.
- Functional Alignment Metrics
  - centered kernel alignment (CKA)
  - 
- Clustering and Dimensionality Reduction
  - PCA, t-SNE, UMAP
  - Cluster the neural activity data and measure the similarity of clusters across conditions or networks.
#TODO:

## Paper
- [Quantifying Differences in Neural Population Activity With Shape Metrics](https://www.biorxiv.org/content/10.1101/2025.01.10.632411v1.full)
- Ability to measure functional variability and relate neural geometry to behavior
- Distance Metrics should statisfie the triangle inequality
  - Procrustes distance (resistent to overfitting, no parameters, insensitive to certain neural tuning differences #TODO: which one?)

Done:
- Introduce a general framework for comparing neural population activity in terms of shape distances.
- Shape differences are quantified after orthogonal geometric transformations (translation, normalization, rotation). 
- In this case the Procrustes distance is used, but any shape distance metric that satisfies the triangle inequality can be used to create downstream analyses like clustering, classification, and regression.
- They demonstrate the approach on different datasets spanning multiple behavioral tasks
- Quantify differences in neural population activity using shape metrics that are insightful and easy to use.

- Highlights the potential to measure functional variability across subjects, brain regions and behavioral tasks.

#### Applied to 
#TODO:
- Neural population activity

### Method
- Orthogonal Geometric transformations $\rightarrow$ shape metric

#### Calculation Steps
1. **Landmark Representaion**: Each shape (e.g., neural activity pattern) is represented by a set of NN landmark points in a high-dimensional space.
2. **Whitening**:
   1. **Translation** $(t)$: Subtract the mean of each dimension from the data points to center them around the origin.
   2. **Scaling** $(s)$: Scale the data points to have unit variance, ensuring that all dimensions contribute equally to the distance metric.
3. **Alignment**: 
   1. **Rotation** $(R)$: Find the optimal rotation matrix that aligns the shapes in a way that minimizes the distance between corresponding points.
4. **Distance Calculation**: The Procrustes distance is defined as the minimum sum of squared Euclidean distances between the optimally aligned points of the two shapes:
```math
dProc(X,Y)=min_{R,t,s} \| sRX + t - Y \|_F
```
where $(R)$ is a rotation matrix, $(t)$ is a translation vector, $(s)$ is a scaling factor, and $(|\cdot|_F)$ is the Frobenius norm.

#### Distance Metrics
Table 1: Distance metrics for shape comparison

|Metric|Explanation|Pros|Cons|Limitations|
|---|---|---|---|---|
|Procrustes Distance|Measures shape similarity by aligning matrices via rigid transformations (rotation, translation, scaling) to minimize Euclidean distance.|Handles rotations and scaling; robust for rigid shape comparisons; computationally efficient for small matrices.|Sensitive to noise; assumes matrices can be aligned rigidly.|Limited to rigid transformations; struggles with non-rigid deformations or unequal dimensions.|
|One-to-One Matching|Computes distance by finding optimal point-to-point correspondences between matrix elements, often using assignment algorithms (e.g., Hungarian method).|Precise for exact correspondences; effective for matrices with equal sizes.|Computationally expensive for large matrices; sensitive to outliers.|Requires equal number of points; fails with partial correspondences or significant shape differences.|
|Soft Matching Distance|Uses probabilistic or soft assignments to measure similarity, allowing flexible correspondences (e.g., via Gaussian Mixture Models or optimal transport).|Handles partial correspondences; robust to noise and unequal dimensions; supports non-rigid transformations.|High computational cost; requires parameter tuning (e.g., regularization).|Complexity increases with matrix size; may need careful initialization for convergence.|

## Citing this Paper
#TODO: 