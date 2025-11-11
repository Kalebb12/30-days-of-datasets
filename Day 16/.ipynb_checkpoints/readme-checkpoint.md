# Anime Recommendation System

This project is an **Anime Recommendation System** built to help users discover new anime based on their preferences. It leverages anime metadata such as genre, popularity, number of episodes, and synopsis to provide tailored recommendations.

---

## Features

- **Search by Title**: Users can look up anime titles. The system now converts all titles to **lowercase** to ensure more consistent and error-free lookups.
- **Genre-based Recommendations**: Suggests anime with similar genres to the one you like.
- **Popularity and Episodes Filtering**: Recommendations consider anime popularity and episode count for better suggestions.
- **Synopses Analysis**: Uses anime descriptions to match similar storylines and themes.

---

## Dataset
cite [kaggle dataet](https://www.kaggle.com/datasets/alexeiluchian/mal-anime-dataset)
The system uses a dataset containing the following fields:

| Field       | Description |
|-------------|-------------|
| `title`     | Name of the anime |
| `score`     | User rating score (0-10) |
| `genres`    | Genres of the anime |
| `episodes`  | Number of episodes |
| `synopsis`  | Short summary of the anime |
| `popularity`| Popularity ranking |

**Note:** All titles are converted to lowercase to ensure accurate and case-insensitive lookups.

---

## How It Works

1. **Preprocessing**: 
    - Convert all anime titles to lowercase.
    - Clean and normalize genre, synopsis, and other metadata.
2. **User Input**: 
    - User provides an anime title they like.
3. **Recommendation Algorithm**:
    - Finds the anime in the dataset.
    - Computes similarity based on genres, synopsis, popularity, and episodes.
    - Returns the top recommended anime.
4. **Output**:
    - A list of anime recommendations with details including title, genres, score, and episode count.

---

## Usage

```python
# Lookup title (case-insensitive)
title = "naruto"  # can be "Naruto" or "NARUTO"
recommendations = recommend(title)

for anime in recommendations:
    print(f"{anime['title']} - {anime['genres']} - Score: {anime['score']}")
