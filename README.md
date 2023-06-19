# Drug Discovery Project - ALDH1 Inhibitor Identification
This project aims to accelerate the drug discovery process by leveraging computer-assisted drug discovery (CADD) techniques to identify potential inhibitors of the enzyme Aldehyde dehydrogenase (ALDH1). ALDH1 plays a crucial role in regulation and metabolism and has been implicated in several diseases, including cancer, Alzheimer's disease, and cardiovascular disease.

## Objective
The objective of this project is to utilize data analysis and computational approaches to identify novel inhibitors of ALDH1 from a larger set of untested molecules. The project focuses on a dataset of 1000 molecules that have been annotated for their ability to modulate ALDH1. Using this dataset, the goal is to predict and select the top 100 molecules, out of the big file of 10K molecules, that are most likely to inhibit ALDH1.

## Dataset Description
The test dataset consists of 1000 molecules, each represented by a Simplified Molecular Input Line Entry System (SMILES) string, which encodes the 2D molecular structure for database usage. For each of these molecules, it is known whether it inhibits ALDH1, with a value of 1 indicating inhibition and 0 indicating no inhibition.

## Data Analysis Pipeline
1. Molecular Descriptors: The RDKit Python package is used to generate a list of 208 molecular descriptors for each molecule in the dataset. These descriptors capture various molecular characteristics and are converted into numerical values for further analysis.

2. Data Preprocessing: The molecular descriptors are scaled using standard scaling to prevent bias. Dimensionality reduction techniques are applied to reduce the number of descriptors. This includes removing missing-valued descriptors (NaN), eliminating high correlation between descriptors (randomly removing one of two variables with a correlation above 90%), removing rows with only zero-values, eliminating duplicated rows, and applying a low-variance filter.

3. Principal Component Analysis (PCA): PCA is performed on the preprocessed dataset to further reduce its dimensionality. The cumulative explained variance is plotted to determine the number of principal components (PCs) required to capture 70% of the data.

4. Machine Learning Model: A K-Nearest Neighbors is employed as the machine learning technique on the cleaned dataset and reduced molecular descriptors. It is based on the principle that similar data points tend to belong to the same class or have similar output values. In k-NN, the "k" refers to the number of nearest neighbors considered for decision-making.

5. Prediction on Novel Dataset: The trained K-Nearest Neighbors is applied to a novel dataset of 10,000 molecules with unknown binding affinity towards ALDH1. The essential molecular descriptors identified through PCA are incorporated into the analysis. The likelihood of each "unknown" molecule binding to ALDH1 is evaluated, facilitating the identification of the top 100 molecules with the highest probability of exhibiting binding affinity.

## Installation and Usage
To reproduce the results of this project, please follow these steps:

1. Download the file "CADD_technologies_solution".
<<<<<<< HEAD
2. Run the file:\
Kernel --> Restart & Run All

=======
2. Run the file:

Kernel --> Restart & Run All

>>>>>>> 93c8db3b972351b16d08b6ffef20cb224ead92f4
3. The final output will include the top 100 molecules from the novel dataset with the highest probability of exhibiting binding affinity to ALDH1. The top 100 molecules is saved to the file "final_top100".

## Conclusion
This project demonstrates the application of computer-assisted drug discovery techniques for the identification of potential ALDH1 inhibitors. By leveraging data analysis, molecular descriptors, and machine learning, the project aims to accelerate the drug discovery process and facilitate the development of novel medicinal drugs for the treatment of diseases associated with ALDH1 dysregulation.
