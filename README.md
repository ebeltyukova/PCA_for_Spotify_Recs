# PCA for Spotify Music Recommendation System

## Project Overview
This project is a **Music Recommendation System** designed to provide personalized song recommendations based on input criteria. Users can specify the name of a song, the artist, and their preferences for features such as danceability, loudness, and instrumentalness. The system identifies the song’s cluster using pre-computed clustering results, matches it with similar songs in the same cluster, and refines the recommendations based on the specified preferences.

## Objective
The primary objective of this project is to create a robust and user-friendly music recommendation system that leverages unsupervised machine learning techniques (clustering) to group songs and provides recommendations tailored to the user’s musical taste.

---

## Key Features

1. **Cluster-Based Song Matching**:
   - Songs are grouped into clusters based on their audio features (e.g., danceability, loudness, instrumentalness) using Principal Component Analysis (PCA) and clustering algorithms.
   - The system retrieves the cluster of the queried song and selects similar songs within the same cluster.

2. **User Input Customization**:
   - Users can input:
     - A song name and artist.
     - Preferences for audio features (e.g., danceability, loudness, instrumentalness).

3. **Feature-Based Filtering**:
   - Songs in the cluster are scored based on their similarity to the user’s preferences for audio features.
   - The closest matches are selected as recommendations.

4. **Random Sampling of Recommendations**:
   - The system selects a random subset of 5 songs from the top 15 matches to add diversity to recommendations.

---

## How It Works

1. **Data Preparation**:
   - Audio features (e.g., danceability, loudness, instrumentalness) are extracted for a large set of songs.
   - Dimensionality reduction using PCA is applied to project features into a lower-dimensional space.
   - Clustering is performed on the reduced data, assigning each song to a cluster.

2. **Cluster Lookup**:
   - Given a song and artist name, the system identifies the cluster to which the song belongs.

3. **Recommendation Generation**:
   - Songs within the same cluster are filtered based on similarity to the user’s specified features.
   - The top 15 matches are sorted by distance (feature similarity) and deduplicated to ensure unique recommendations.
   - A final list of 5 songs is randomly selected from the refined list.

4. **Interactive UI**:
   - The system uses `ipywidgets` to create an interactive interface where users can input their preferences and view recommendations in real-time.

---

## Dependencies

- **Python Libraries**:
  - `pandas`: For data manipulation.
  - `numpy`: For numerical operations.
  - `scikit-learn`: For PCA and clustering.
  - `ipywidgets`: For creating the interactive user interface.

---

## File Descriptions

- **`data/`**: Contains the dataset with song features and clustering results.
- **`notebooks/`**: Jupyter notebooks with the implementation of the recommendation logic.
- **`src/`**: Python scripts for preprocessing, clustering, and recommendation generation.
- **`README.md`**: This file, providing an overview of the project.

---

## Usage Instructions

1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_folder>
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the Jupyter notebook or Python script to start the recommendation system.

4. Use the interactive UI to input your preferences and get song recommendations.

---

## Future Enhancements

- Integration with music streaming platforms to fetch real-time data.
- Support for additional features such as lyrics, mood, and genres.
- Enhanced machine learning models for more accurate clustering and recommendations.
- Deployment as a web application for broader accessibility.


