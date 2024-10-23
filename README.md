
# EEG Motor Imagery Classification and Clustering 

This project focuses on classifying and clustering EEG data collected during motor imagery tasks. The aim is to apply advanced signal processing techniques for **feature extraction**, followed by **dimensionality reduction** and **clustering** to understand EEG signals better. We also perform **classification** of motor imagery tasks using a variety of machine learning algorithms.

## Project Overview

The project uses EEG data to classify motor imagery tasks, focusing on preprocessing, filtering, feature extraction, and classification. In addition, clustering methods are employed to find patterns within the data. The key tasks are:

1. **EEG Data Preprocessing**:
   - Bandpass filtering (Mu band: 8–12 Hz, Beta band: 13–30 Hz).
   - Spatial filtering using **Common Average Reference (CAR)** and **Laplacian** filters.

2. **Feature Extraction**:
   - **Common Spatial Patterns (CSP)** for maximizing variance between classes.
   - **Principal Component Analysis (PCA)** and **Linear Discriminant Analysis (LDA)** for dimensionality reduction.

3. **Clustering**:
   - Unsupervised clustering using **K-Means** and **DBSCAN**.
   - Visualizing cluster results using PCA-reduced features.

4. **Classification**:
   - Supervised classification using algorithms like **MLP Neural Networks**, **Gradient Boosting**, **AdaBoost**, and **K-Nearest Neighbors (KNN)**.
   - Comparison of model performance across different feature extraction techniques.

## Datasets

We use two datasets containing EEG data:
- **Dataset A**: BCICIV_calib_ds1a.mat
- **Dataset B**: BCICIV_calib_ds1d.mat

Both datasets contain continuous EEG signals and target markers for motor imagery tasks, sampled at 100 Hz.

## Workflow

### 1. Data Preprocessing
   - **Loading Data**: The EEG signals are loaded and converted into microvolts.
   - **Bandpass Filtering**: Signals are filtered to isolate the Mu (8–12 Hz) and Beta (13–30 Hz) frequency bands using a **Butterworth filter**.
   - **Spatial Filtering**: 
     - **CAR**: Reduces noise by re-referencing each channel to the average of all channels.
     - **Laplacian Filter**: Enhances local differences by emphasizing focal brain activity.

### 2. Feature Extraction
   - **Common Spatial Patterns (CSP)**: Used to extract spatial filters from motor imagery tasks for classification.
   - **Principal Component Analysis (PCA)**: Reduces data dimensionality while preserving 95% of the variance.
   - **Linear Discriminant Analysis (LDA)**: Projects data into a lower-dimensional space with maximal class separability.

### 3. Clustering
   - **K-Means**: Clusters EEG data into groups using CSP-extracted features.
   - **DBSCAN**: Applies density-based clustering to EEG features, using grid search to find optimal parameters (`eps`, `min_samples`).

### 4. Classification
   - Various classifiers are applied to the extracted features to classify motor imagery tasks, including:
     - **MLP Neural Networks**
     - **Gradient Boosting**
     - **AdaBoost**
     - **K-Nearest Neighbors (KNN)**

### 5. Visualization
   - **t-SNE**: Visualizes high-dimensional EEG data after feature extraction.
   - **PCA and Clustering Plots**: Shows clustering results and how well different clusters are separated.

## Results

- **Best Feature Extraction Method**: CSP proved to be the most effective feature extraction method.
- **Best Classifier**: MLP Neural Networks achieved the highest classification accuracy (90% on Dataset A and 82% on Dataset B).
- **Clustering**: DBSCAN and K-Means provided insight into the separability of EEG features.

## Installation and Setup

### Prerequisites

- Python 3.8+
- Required libraries:
  - `numpy`
  - `scipy`
  - `scikit-learn`
  - `matplotlib`
  - `mne`

### Running the Code
To run the PCA and clustering analysis, execute:
```bash
EEG_Classification_Clustering.ipynb
```

## Project Structure

- `EEG_Classification_Clustering.ipynb`: Contains code of all parts
- `/datasets`: Contains two datasets

## Conclusion

This project successfully demonstrates how to preprocess, filter, and extract features from EEG data for motor imagery tasks. **CSP** is the most effective method for feature extraction, while **MLP Neural Networks** provide the best classification results. Unsupervised methods like **DBSCAN** and **K-Means** offer insights into data clustering and the separability of different motor imagery tasks.

For detailed information and instructions, please refer to the [Project Report](EEG_Motor_Imagery_Classification_and_Clustering_Report.pdf).

