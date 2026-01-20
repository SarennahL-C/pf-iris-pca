# Iris Dataset — Principal Component Analysis and Unsupervised Clustering

This project applies **Principal Component Analysis (PCA)** and unsupervised clustering techniques to the classic Iris dataset, completed as part of a structured machine learning task. The objective was to explore dimensionality reduction, investigate redundancy between features, and assess whether clustering techniques applied to PCA-transformed data could identify the three known Iris species.

While the task followed a guided notebook structure, emphasis was placed on **careful interpretation of results**, understanding the mathematical intent of PCA, and critically evaluating the outcomes of unsupervised learning methods.

### What’s in this repository

- **Jupyter Notebook:** step-by-step analysis (`PCA_task.ipynb`)    
- **Images:** visuals
- **Source data:** csv dataset (`Iris.csv`)  
- **Requirements:** Python dependencies (`requirements.txt`)

---

### Project Context

The Iris dataset contains four numerical features describing flower morphology:

- sepal length  
- sepal width  
- petal length  
- petal

These variables are known to exhibit strong correlations, particularly between petal measurements. This makes the dataset well suited for dimensionality reduction techniques such as PCA, which aim to:

- reduce redundancy between features  
- transform correlated variables into independent components  
- preserve as much variance as possible in fewer dimensions  

The task required performing PCA with three components, visualising the transformed data, and applying clustering methods to assess whether the species structure could be recovered without labels.

---

## Exploratory Analysis

Initial exploration confirmed the presence of strong correlations between original features, particularly among petal measurements. These correlations motivated the application of PCA as a method for transforming the feature space into a set of uncorrelated components.

A correlation heatmap was used to visualise positive and negative relationships prior to transformation, providing a baseline for comparison after PCA.

---

## Principal Component Analysis

After scaling the data, PCA was applied with **three principal components**. The eigenvectors for PetalLengthCm and PetalWidthCm are very closely aligned, indicating a strong relationship between them. In contrast, SepalLengthCm and SepalWidthCm have distinct orientations. From this biplot, the three principal components in the data are SepalLengthCm, SepalWidthCm and PetalWidthCm.

![Biplot with eigenvectors for four features. The eigenvectors for petal width and petal length are very close together. The eigenvector of sepal length and sepal width are almost perpendicular, with sepal length having a similar direction to petal width and petal length.](iris-biplot.png)

### Interpretation of Principal Components

Analysis of the transformed data revealed that:

- The principal components are **independent**, confirming that PCA successfully removed inter-feature correlations.
- The first principal component (PC1) retained a **bimodal distribution**, reflecting the structure present in the original petal length and petal width features.
- Subsequent components captured decreasing proportions of variance, as expected.

A pair grid of the PCA-transformed data showed that:

- The bimodality of PC1 remained visible after transformation.
- Correlations between components were effectively null, confirming successful dimensionality reduction.
- Structure was preserved in the data, but not in a way that clearly separated all species.

This demonstrates an important property of PCA: it preserves variance, not class separability.

---

## Clustering Analysis

Both **hierarchical clustering** and **k-means clustering** were applied to the PCA-transformed data.

### Key Findings

- The clusters produced by k-means **did not correspond to the original species labels**.
- Despite reducing redundancy and dimensionality, clustering techniques were unable to recover the three Iris species.
- This outcome highlights that:
  - PCA does not guarantee improved class separability
  - Unsupervised clustering identifies structure based on variance, not labels
  - Biological class boundaries do not necessarily align with variance-based groupings

Rather than indicating a failure of the models, this result illustrates a fundamental limitation of unsupervised learning.

---

### Insights and Interpretation

Several important insights emerged from this analysis:

- PCA successfully removed correlations and produced independent components.
- The dominant variance in the dataset is driven primarily by petal measurements.
- Although two species exhibit partial separation, the third overlaps significantly in feature space.
- As a result, clustering algorithms struggle to identify three distinct groups without supervision.

This reinforces the distinction between:

- **dimensionality reduction** (preserving variance)
- **classification** (learning decision boundaries)

and demonstrates why supervised models are often required when class separation is the primary goal.

---

### Skills Demonstrated

- Exploratory data analysis  
- Correlation analysis and interpretation  
- Principal Component Analysis (PCA)  
- Feature scaling and transformation  
- Biplot interpretation  
- Hierarchical clustering  
- K-means clustering  
- Critical evaluation of unsupervised learning results  
- Clear analytical reasoning and documentation  

---

### Requirements

Install the required Python dependencies with: `pip install -r requirements.txt`

---

### Why this project belongs in my portfolio

Unsupervised learning techniques often require deeper interpretation than supervised models, as there is no predefined “correct” outcome. This project demonstrates my ability to:
- understand what PCA is mathematically designed to achieve
- interpret transformed feature spaces rather than treating them as abstract outputs
- recognise the limitations of clustering methods
- communicate why a result is meaningful even when it does not match expected labels

It complements my supervised learning projects by showcasing conceptual understanding, analytical judgement, and careful interpretation of unsupervised machine learning techniques.
