# 🎬 Content-Based Movie Recommendation System using NLP

## 📌 Project Overview

This project is a **Content-Based Movie Recommendation System** built using Natural Language Processing (NLP) techniques. 

The system recommends the **Top 5 movies** similar to a given movie based on:
- Overview
- Genres
- Keywords
- Top 3 Cast Members
- Director

It uses **CountVectorizer** for feature extraction and **Cosine Similarity** to measure similarity between movies.

---

## 🗂 Dataset Used

- TMDB 5000 Movies Dataset
- TMDB 5000 Credits Dataset

These datasets contain movie metadata such as:
- Title
- Overview
- Genres
- Keywords
- Cast
- Crew

---

## ⚙️ Technologies & Libraries Used

- Python
- Pandas
- NumPy
- Scikit-learn
- NLTK
- AST (for parsing JSON-like strings)

---

## 🧠 NLP Techniques Used

### 1️⃣ Text Preprocessing
- Removed null values
- Removed duplicate records
- Converted stringified JSON columns into Python lists using `ast.literal_eval`

### 2️⃣ Feature Engineering
- Extracted:
  - Genres
  - Keywords
  - Top 3 Cast Members
  - Director
- Removed spaces between names (e.g., `James Cameron → JamesCameron`)
- Combined all features into a single column called `tags`

### 3️⃣ Text Vectorization
- Used `CountVectorizer`
- Limited to `max_features=5000`
- Removed English stopwords

### 4️⃣ Stemming
- Used `PorterStemmer`
- Reduced words to their root form (e.g., acting → act)

### 5️⃣ Similarity Measurement
- Used `Cosine Similarity`
- Measures similarity between movie vectors
- Value ranges from 0 (no similarity) to 1 (high similarity)

---

## 🔍 How the Recommendation Works

1. User inputs a movie name
2. System finds the index of the movie
3. Computes cosine similarity scores
4. Sorts movies in descending order
5. Returns Top 5 most similar movies

---

## 💻 Example Usage

```python
recommend('Pirates of the Caribbean: At World\'s End')
```

### Output:
```
Pirates of the Caribbean: Dead Man's Chest
The Curse of the Black Pearl
Prince of Persia: The Sands of Time
The Lone Ranger
National Treasure
```

---

## 📊 Core Function

```python
def recommend(movie):
    movie_index = new_df[new_df['title'] == movie].index[0]
    distances = similarity[movie_index]
    sorted_distances = sorted(list(enumerate(distances)),
                              reverse=True,
                              key=lambda x: x[1])
    
    for i in sorted_distances[1:6]:
        print(new_df.iloc[i[0]].title)
```

---

## 🚀 Future Improvements

- Deploy using Streamlit
- Add TMDB API to fetch posters
- Improve recommendations using TF-IDF
- Implement hybrid recommendation system
- Add user-based collaborative filtering

---

## 📌 Key Learning Outcomes

- Practical implementation of NLP
- Feature engineering on structured + unstructured data
- Vectorization using CountVectorizer
- Understanding cosine similarity in high-dimensional space
- Building a real-world recommendation engine

---

## 👨‍💻 Author

Manoj Kumar  
Mechanical Engineering Graduate | Aspiring Data Analyst & Data Scientist  

---

## ⭐ If You Like This Project

Give it a star on GitHub!
