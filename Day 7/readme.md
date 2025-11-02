# 🎬 Movie Recommendation System (Content-Based Filtering)

This project builds a **content-based movie recommendation system** using **TF-IDF vectorization** and **cosine similarity**. It recommends movies that are similar in content (genres, descriptions, and taglines) to a given title.

---

## 📁 Dataset Overview

The project uses two main datasets:

### 1. `ratings-small.csv`
| Column | Description |
|---------|-------------|
| `userId` | Unique identifier for each user |
| `movieId` | Unique identifier for each movie |
| `rating` | User rating (0.5–5.0 scale) |
| `timestamp` | Time of rating in Unix format |

### 2. `movies_metadata.csv`
Contains detailed movie information such as title, overview, tagline, and genres.

---

## 🧹 Data Preprocessing

### 1. Load the Data
```python
movies_metadata = pd.read_csv('data/movies_metadata.csv', low_memory=False)
```
### 2. Handle Missing Values
```python
movies_metadata['overview'] = movies_metadata['overview'].fillna('')
movies_metadata['tagline'] = movies_metadata['tagline'].fillna('')
movies_metadata['genres'] = movies_metadata['genres'].fillna('')
```

### 3. Extract Genres
```python
def extract_genres(genres_str):
    try:
        genres = eval(genres_str)
        return ' '.join([g['name'] for g in genres])
    except:
        return ''
movies_metadata['genres_str'] = movies_metadata['genres'].apply(extract_genres)
```

### 4. Combine text features
```python
movies_metadata['combined_text'] = (
    movies_metadata['genres_str'] + ' ' +
    movies_metadata['overview'] + ' ' +
    movies_metadata['tagline']
)
```

## Example usage
```python
sample_movie = "Mad Dog Time"
recommendations = get_movie_recommendations(sample_movie)
print(recommendations)
```
## Summary
This notebook demonstrates how text-based features (genres, overview, tagline) can power a content-based movie recommender system. By combining natural language processing (NLP) with similarity metrics, we can deliver personalized movie suggestions without relying on user ratings.



