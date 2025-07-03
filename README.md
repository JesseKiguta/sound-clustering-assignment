# Sound Data Clustering with K-Means and DBSCAN

This project explores unsupervised clustering of [unlabelled sound data](https://drive.google.com/file/d/1bme1IuScdIWjzFkYPOcWzFOgD50MS_zR/view) using MFCC-based feature extraction and two popular clustering algorithms: **K-Means** and **DBSCAN**. It includes preprocessing, dimensionality reduction, clustering evaluation, and visualization.

---

## Setup

### 1. Clone the repo

```
git clone https://github.com/JesseKiguta/sound-clustering-assignment.git
cd sound-clustering
```

### 2. Install dependencies
Install core libraries manually:

```
pip install librosa scikit-learn matplotlib seaborn kneed mpl_toolkits.mplot3d
```

---


## Pipeline Overview
**1. Feature Extraction**

- Converts audio files to MFCCs (Mel-Frequency Cepstral Coefficients)
  
- Uses the mean MFCC vector as the feature representation

**2. Preprocessing**

- Applies Standard Scaling to normalize features

- Uses PCA to reduce dimensions for clustering and visualization

**3. Clustering Algorithms**

- K-Means (parameter: n_clusters, chosen using the Elbow Method)

- DBSCAN (parameters: eps, min_samples, tuned using k-distance and kneed)

**4. Evaluation Metrics**

- Silhouette Score (Higher is better)

- Davies-Bouldin Index (Lower is better)

**5. Visualization**

- 2D PCA scatter plots showing clusters

- k-distance plot to determine optimal DBSCAN eps

## Findings
| Algorithm | Silhouette Score | Davies-Bouldin Index |
|-----------|------------------|----------------------|
| K-Means   | 0.3605           | 1.0257               |
| DBSCAN    | 0.1768           | 4.2105               |


K-Means outperformed DBSCAN in this case, producing better-separated and more compact clusters.

DBSCAN struggled with parameter sensitivity and cluster merging, despite tuning.

## Real-World Relevance
This project reflects real-world clustering challenges, such as:

- Selecting the right algorithm

- Feature scaling and dimensionality reduction

- Evaluating clusters without ground truth labels

- Handling density variation in data


## License
This project is for educational purposes and open for extension or reuse.

## Author
Created by Jesse Kiguta.
Feel free to reach out or fork the project!
