
<div align="center">

# 🎵 Spotify Genre Segmentation

### Building an Automated Music Recommendation System Using Machine Learning

<img src="https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/Machine%20Learning-K--Means-orange?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Scikit--Learn-ML-red?style=for-the-badge&logo=scikitlearn"/>
<img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge"/>

**Discover similar songs using audio features, clustering, and cosine similarity.**

</div>

---

## 📌 Project Overview

This project focuses on developing an automated music recommendation system inspired by Spotify.

It uses Machine Learning techniques to group songs based on their audio characteristics and recommend similar tracks using content-based filtering.

The project includes data preprocessing, exploratory data analysis, correlation analysis, K-Means clustering, PCA visualization, and cosine similarity-based song recommendations.

## 🎯 Project Objectives

- Analyze Spotify music datasets.
- Understand audio characteristics of different music genres.
- Perform data cleaning and preprocessing.
- Explore relationships between audio features.
- Apply feature scaling and dimensionality reduction.
- Group similar songs using K-Means clustering.
- Build a content-based music recommendation system.
- Recommend songs based on audio similarity.

## 📂 Dataset Information

**Dataset:** `spotify.csv`

- Total Tracks: 32,833
- Audio Features: 9
- Genre and Subgenre Information
- Track and Artist Metadata
- Track Popularity Information

### Audio Features

| Feature | Description |
|---|---|
| Danceability | How suitable a track is for dancing |
| Energy | Intensity and activity of a track |
| Loudness | Overall loudness |
| Speechiness | Presence of spoken words |
| Acousticness | Acoustic characteristics |
| Instrumentalness | Probability of containing no vocals |
| Liveness | Presence of an audience |
| Valence | Musical positivity |
| Tempo | Speed of the track in BPM |

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming |
| Pandas | Data manipulation |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Scikit-learn | Machine Learning |
| Jupyter Notebook | Development environment |

## ⚙️ Project Workflow

1. Import required libraries.
2. Load Spotify dataset.
3. Check missing values and duplicates.
4. Clean the dataset.
5. Perform feature engineering.
6. Conduct Exploratory Data Analysis (EDA).
7. Analyze audio feature distributions.
8. Generate correlation matrix.
9. Standardize audio features.
10. Find optimal clusters using Elbow Method and Silhouette Score.
11. Apply K-Means clustering.
12. Visualize clusters using PCA.
13. Analyze cluster and genre relationships.
14. Build a song recommendation model.
15. Evaluate the clustering model.

## 🧹 Data Preprocessing

The following preprocessing operations are performed:

- Check missing values.
- Remove records with missing critical text fields.
- Remove duplicate track IDs.
- Convert album release dates into datetime format.
- Extract release year.
- Convert track duration from milliseconds to minutes.
- Identify potential outliers using the IQR method.

### Feature Engineering

Two additional features are created:

**1. Release Year**

Extracted from the album release date.

**2. Duration in Minutes**

Duration is converted from milliseconds into minutes.

## 📊 Exploratory Data Analysis (EDA)

The project performs the following visual analyses:

- Playlist genre distribution.
- Top 15 playlist subgenres.
- Audio feature distributions.
- Track popularity analysis.
- Audio features across different genres.
- Release year trends.
- Relationships between energy, loudness, danceability, and valence.
- Correlation heatmap.

### Key Observations

- Energy and loudness have a strong positive correlation.
- Energy and acousticness have a strong negative correlation.
- Track popularity has weak correlation with individual audio features.
- Different music genres show different audio characteristics.

## 🧠 Machine Learning Algorithm

### K-Means Clustering

K-Means is used to group songs with similar audio characteristics.

**Implementation:**

- StandardScaler for feature scaling.
- Elbow Method for selecting the number of clusters.
- Silhouette Score for cluster evaluation.
- K-Means with 6 clusters.
- Random state: 42.
- PCA for 2D cluster visualization.

### Optimal Number of Clusters

The project evaluates cluster counts from:

`k = 2 to k = 10`

Based on the Elbow Method and Silhouette analysis, the final model uses:

**Number of Clusters: K = 6**

## 📉 Dimensionality Reduction

### Principal Component Analysis (PCA)

PCA is used to reduce the nine-dimensional audio feature space into two principal components.

This helps visualize:

- K-Means clusters.
- Actual playlist genres.
- Relationships between discovered clusters and genres.

## 🎧 Music Recommendation System

### Content-Based Filtering

The recommendation engine uses audio features to identify similar songs.

**Working Process:**

1. Select a song from the dataset.
2. Retrieve its scaled audio feature vector.
3. Identify its K-Means cluster.
4. Calculate cosine similarity.
5. Rank songs based on similarity scores.
6. Return the top recommended tracks.

### Recommendation Function

```python
recommend_songs(
    song_name,
    n_recommendations=10,
    same_cluster_only=True
)
```

**Parameters:**

| Parameter | Description |
|---|---|
| song_name | Input track name |
| n_recommendations | Number of recommendations |
| same_cluster_only | Restrict recommendations to the same cluster |

**Example:**

```python
recommend_songs(
    'Memories - Dillon Francis Remix',
    n_recommendations=10
)
```

### Similarity Calculation

Cosine similarity measures how similar two songs are based on their scaled audio feature vectors.

\[
Similarity(A,B)=\frac{A\cdot B}{\|A\|\|B\|}
\]

## 📈 Model Evaluation

The clustering model is evaluated using:

- Silhouette Score
- Inertia
- Cluster Size Distribution
- PCA Visualization
- Cluster-to-Genre Comparison

The notebook calculates the final Silhouette Score and Inertia after training.

## 📁 Project Structure

```text
Spotify-Genre-Segmentation/
│
├── Spotify_Genre_Segmentation.ipynb
│
├── spotify.csv
│
├── README.md
│
└── Visualizations/
    ├── genre_distribution.png
    ├── feature_distributions.png
    ├── correlation_matrix.png
    ├── optimal_k.png
    └── cluster_visualization.png
```

## 🚀 Installation and Execution

### Step 1: Clone Repository

```bash
git clone YOUR_REPOSITORY_URL
```

### Step 2: Navigate to Project

```bash
cd Spotify-Genre-Segmentation
```

### Step 3: Install Required Libraries

```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

### Step 4: Launch Jupyter Notebook

```bash
jupyter notebook
```

### Step 5: Open Notebook

Open:

`Spotify_Genre_Segmentation.ipynb`

Make sure `spotify.csv` is available in the same directory.

## 🔮 Future Enhancements

- Develop a web-based music recommendation application.
- Integrate Spotify API.
- Build an interactive recommendation dashboard.
- Implement collaborative filtering.
- Develop a hybrid recommendation system.
- Improve recommendations using user listening history.
- Deploy the recommendation model using Flask or FastAPI.

## 🏁 Conclusion

This project demonstrates how Machine Learning can be used to analyze music characteristics, discover patterns, and build an automated music recommendation system.

K-Means clustering groups songs based on their audio features, while cosine similarity identifies acoustically similar tracks.

The final system provides a foundation for building personalized music recommendation applications inspired by Spotify.

---

<div align="center">

### 🎵 Music + Machine Learning = Smart Recommendations

**Built using Python, K-Means Clustering and Cosine Similarity**

</div>
