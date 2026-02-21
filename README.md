# Amazon Music Clustering: Automatic Genre Discovery

## 📌 Project Overview
With millions of songs available on digital streaming platforms, manually categorizing tracks into genres is an impossible task. This project utilizes **Unsupervised Machine Learning** to automatically group songs into meaningful clusters based on their unique audio characteristics. By analyzing features like tempo, energy, and danceability, we create a model that organizes music into cohesive groups—representing potential genres or moods—without the need for human labels.

## 🚀 Business Use Cases
*   **Personalized Playlist Curation:** Enhancing user experience by automatically generating playlists of sonically similar tracks.
*   **Improved Song Discovery:** Increasing platform engagement by suggesting new tracks based on a user’s preferred audio profile.
*   **Artist Analysis:** Enabling artists and producers to identify competitive landscapes within specific audio clusters.
*   **Market Segmentation:** Helping streaming services analyze listening patterns to optimize marketing spend and promotional offers.

## 🛠️ Technologies Used
*   **Python 3.8+**
*   **Pandas:** Data manipulation and analysis.
*   **Scikit-Learn:** Machine Learning algorithms (K-Means, DBSCAN, Agglomerative Clustering) and preprocessing.
*   **Matplotlib/Seaborn:** Data visualization.
*   **PCA/t-SNE:** Dimensionality reduction for cluster visualization.

## 📊 Dataset & Feature Selection
The project uses audio metadata containing various descriptors. To represent the "sound" of a track effectively, the following features are utilized:
*   **Rhythmic:** `danceability`, `tempo`.
*   **Atmospheric:** `energy`, `loudness`, `valence`.
*   **Textural:** `acousticness`, `instrumentalness`, `speechiness`, `liveness`.
*   **Temporal:** `duration_ms`.

## 📈 Project Workflow

### 1. Data Exploration & Preprocessing
*   Handle missing data and remove duplicates.
*   **Feature Dropping:** Identifiers like `track_name`, `artist_name`, and `track_id` are removed to prevent the model from leaning on non-audio data.
*   **Normalization:** Scaling data using `StandardScaler` to ensure all features contribute equally to distance calculations.

### 2. Dimensionality Reduction
*   Implementation of **PCA** (Principal Component Analysis) or **t-SNE** to reduce the 10D feature space into 2D or 3D for human-readable cluster visualization.

### 3. Clustering Implementation
We explore three primary algorithms:
*   **K-Means:** Using the **Elbow Method** (SSE) and **Silhouette Scores** to find the optimal number of clusters ($k$).
*   **DBSCAN:** To identify arbitrary-shaped clusters and detect outlier "noise" tracks.
*   **Agglomerative Clustering:** Using dendrograms to understand the hierarchical relationship between musical styles.

### 4. Evaluation and Interpretation
*   **Metrics:** Use Silhouette Score and Davies-Bouldin Index to validate cluster separation and compactness.
*   **Profiling:** Analyzing the mean feature values of each cluster to assign "Mood" labels (e.g., *High Energy + High Danceability = "Party Tracks"*).

### 5. Visualization
*   Color-coded Scatter Plots (PCA/t-SNE).
*   Heatmaps and Radar Charts for feature comparison across clusters.
*   Distribution plots for individual audio attributes.

## 📂 Expected Output
*   A transformed CSV file containing original song metadata with a new `cluster_label` column.
*   A summary report detailing the "personality" of each identified musical group.
*   A suite of visualizations showing clear segments in the music library.

## 🤝 Contributing
Contributions are welcome! If you have ideas for improving the clustering accuracy or adding new visualization styles, feel free to open a Pull Request.

---   
**Author:** Raji
**Contact:** (https://www.linkedin.com/in/rajarajeswari-baladhandapani/)
