# Day 28 – Spotify Tracks & Artists Analysis

## 📌 Overview

This day's project focused on exploring and analyzing a combined Spotify dataset consisting of track-, artist-, and album‑level information. Two datasets were originally provided (`trackdf` and `spotify df`), and the cleaned version used for analysis merged the important columns into a single structured dataframe.

The objective of Day 28 was to understand trends in track popularity, artist influence, album characteristics, and temporal patterns using exploratory data analysis.

---

## 📂 Dataset Columns

Your final working dataset contained:

* **track_id** (object)
* **track_name** (object)
* **track_number** (int)
* **track_popularity** (int)
* **explicit** (bool)
* **artist_name** (object)
* **artist_popularity** (int)
* **artist_followers** (int)
* **artist_genres** (object)
* **album_id** (object)
* **album_name** (object)
* **album_release_date** (datetime)
* **album_total_tracks** (int)
* **album_type** (object)
* **track_duration_min** (float)

---

## 🧹 Data Cleaning Steps

* Removed duplicate rows to avoid counting the same track multiple times.
* Converted **album_release_date** from string → datetime for time‑based analysis.
* Filtered to keep only the Spotify dataframe version with correct `track_duration_min`.
* Ensured categorical columns (genres, explicit, album_type) retained correct types.

---

## 🔍 Key Analyses Performed

### 1. **Track Popularity Distribution**

You explored how track popularity is distributed across the dataset.

* Most tracks cluster around mid‑range popularity.
* A long‑tail distribution shows a small number of highly popular songs.

### 2. **Artist Popularity vs Track Popularity**

A scatter plot revealed a **strong positive correlation**:

* Higher‑popularity artists tend to release more popular tracks.
* Some outliers appear where less‑popular artists have breakout songs.

### 3. **Genres Field Exploration**

investigated:

* Distribution of genres per artist.
* Multi‑genre artists.
* Which genres correlate with higher popularity.

---

## 📈 Visualizations Included

* Track popularity histogram
* Artist popularity vs. track popularity scatter plot
* Track duration histogram
* Release date timeline
* Explicit vs non‑explicit bar chart
* Album type distribution
* Genre frequency plot

---

## 📝 Possible Next Tasks (for Day 29)

Here are suggested follow‑ups:

1. Build a **track popularity prediction model**.
2. Cluster artists by genre + popularity.
3. Analyze evolution of genres over the years.
4. Investigate relationship between explicit content and popularity.
5. Use NLP on track names to find naming patterns.
6. Compare album vs single performance.
7. Plot artist follower growth (if longitudinal data exists).

---

## ✅ Summary

Day 28 focused on transforming, cleaning, and exploring a rich Spotify dataset. The analyses revealed strong ties between artist influence and track performance, consistent duration patterns, and insightful album- and genre‑level trends.

This README documents the workflow and findings for future reference.
