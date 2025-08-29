"# R-PROJECTS" 
**Predictive Modeling of Aquatic Toxicity using Machine Learning**




This project implements a comprehensive machine learning framework to predict the acute aquatic toxicity of chemical compounds to Daphnia magna, a standard model organism in ecotoxicology. Using a Quantitative Structure-Activity Relationship (QSAR) dataset, we explore the links between molecular structure and toxicity (measured as LC50 values).

The primary goal is to build and evaluate a range of supervised and unsupervised models to not only predict toxicity accurately but also to identify the key molecular descriptors that drive these toxic effects. This work aims to support environmental risk assessment and guide the design of safer chemicals, reducing the reliance on animal testing.

Dataset
The analysis is based on a publicly available QSAR dataset containing 546 organic compounds. For each compound, the dataset includes:

8 Molecular Descriptors (Predictors):

TPSA(Tot): Topological polar surface area

SAacc: Surface area of hydrogen bond acceptors

H-050: Atom-centered fragment descriptor

MLOGP: Logarithm of the partition coefficient (hydrophobicity)

RDCHI: Chi index capturing molecular connectivity

GATS1P: Geary autocorrelation of lag 1, weighted by polarizability

nN: Number of nitrogen atoms

C-040: Presence of specific substructure fragments

1 Response Variable:

LC50: The log-transformed concentration that is lethal to 50% of the Daphnia magna population. A lower value indicates higher toxicity.

Methodology
The project employs a multi-faceted approach, combining data exploration, supervised regression, and unsupervised clustering in R.

1. Exploratory Data Analysis (EDA)
Distribution Analysis: Histograms were used to examine the distribution of the target variable (LC50).

Outlier Detection: Boxplots were generated for each molecular descriptor to identify outliers.

Correlation Analysis: A correlation matrix was used to assess multicollinearity among predictors.

2. Supervised Learning for Toxicity Prediction
Five regression models were implemented and benchmarked to predict LC50 values:

Multiple Linear Regression (MLR): A baseline model to assess linear relationships.

Lasso Regression: Used for feature selection and regularization to create a more parsimonious model.

Regression Tree: A non-linear model to capture decision rules and threshold effects.

Random Forest: An ensemble model to improve predictive accuracy and rank feature importance.

Neural Network (MLP): A fully-connected neural network with a single hidden layer was implemented to capture complex, non-linear relationships between the molecular descriptors and toxicity.

3. Unsupervised Learning for Pattern Discovery
Three unsupervised methods were used to explore the inherent structure of the chemical space:

Principal Component Analysis (PCA): To reduce dimensionality and visualize the variance among compounds.

K-Means Clustering: To identify natural groupings of molecules based on their descriptor profiles.

Network Analysis and Community Detection: Constructed a molecular similarity network where each compound is a node and edges are defined by the cosine similarity of their descriptor profiles. Community detection algorithms (e.g., Walktrap, Louvain) were then applied to identify dense clusters of structurally related molecules.

4. Model Evaluation
Models were evaluated based on:

Root Mean Squared Error (RMSE): To measure prediction error.

R-squared (R²): To quantify the proportion of variance explained by the model.

Key Findings
Best Predictive Model: The Random Forest model demonstrated the highest predictive performance, explaining 57.8% of the variance in toxicity and achieving the lowest RMSE. Its ability to capture non-linear interactions proved superior to simpler linear models.

Most Influential Descriptors: Across all models, three molecular descriptors were consistently identified as the most significant predictors of toxicity:

MLOGP (Hydrophobicity)

RDCHI (Molecular Complexity/Connectivity)

TPSA.Tot (Polar Surface Area)

Structural Insights: Unsupervised methods successfully uncovered latent structures in the chemical space. PCA captured ~66% of the variance in the first two components, and network analysis revealed statistically significant communities of structurally similar molecules, providing a more nuanced grouping than standard clustering.

How to Run This Project
Prerequisites
R installed on your system.

RStudio (Recommended).
