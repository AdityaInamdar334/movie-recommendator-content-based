---

```markdown
# 🎬 Movie Recommender System (Content-Based)

This project is a **content-based movie recommender system** built with Python, NLP techniques, and Streamlit, and deployed on Heroku. It suggests similar movies based on your input, using movie features like title, overview, genre, and keywords.

---

## 🚀 Demo

🔗 **[Live App on Heroku](#)**  
_(Replace with your actual link when deployed)_

---

## 🧠 Project Workflow

Here's how the entire system works, step-by-step:

### 1. 🧲 Dataset Collection
- Movies metadata was collected using the **TMDB 5000 Movie Dataset**.
- The dataset includes movie titles, overviews, genres, keywords, and other metadata.

### 2. 🧹 Data Cleaning
- Dropped unnecessary columns (`homepage`, `production_companies`, etc.)
- Filtered out null values and inconsistencies.
- Converted JSON strings (e.g., genres, keywords) into readable formats.
- Extracted useful features like `genres`, `keywords`, `cast`, `crew` using custom functions.

### 3. 🧬 Feature Engineering
- Selected important content features: `overview`, `genres`, `keywords`, `cast`, `crew`.
- Combined them into a single **"tags"** column for each movie.
- Applied **text normalization** (lowercasing, removing spaces, etc.)

### 4. 🧠 NLP + Vectorization
- Used **Bag of Words** via `CountVectorizer` to transform text data into numerical vectors.
- Set `max_features=5000` and removed English stopwords.
- Calculated **Cosine Similarity** across all movie vectors to find similarities.

### 5. 📊 Recommendation Engine
- When a user selects a movie:
  - Its index is used to fetch its vector.
  - Cosine similarity is calculated with all other movie vectors.
  - Top 5 similar movies are returned (excluding the original).

### 6. 💾 Model Export
- Created and exported two important files using `pickle`:
  - `movie_list.pkl` — stores movie metadata and processed tags.
  - `similarity.pkl` — stores the cosine similarity matrix.

### 7. 🌐 Deployment
- Built a front-end using **Streamlit**.
- Designed a simple and clean UI with movie posters using **TMDB API**.
- Deployed the full app to **Heroku**.

---

## 🛠️ Tech Stack

- Python, Pandas, NumPy
- Scikit-learn (Vectorizer, Similarity)
- Streamlit (Frontend)
- Requests (TMDB API)
- Pickle (model saving)
- Heroku (deployment)

---

## 💻 How to Run Locally

1. **Clone the repo**:
   ```bash
   git clone https://github.com/your-username/movie-recommender.git
   cd movie-recommender
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the app**:
   ```bash
   streamlit run app.py
   ```

---

## 🧾 Sample Recommendation Flow

> User selects **Inception**  
> System fetches its tags → Vectorizes → Finds top 5 closest matches using cosine similarity → Displays posters + names

---

## 📦 Dataset Source

- [TMDB 5000 Movie Dataset (Kaggle)](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)
- [TMDB API](https://developers.themoviedb.org/3)

---

## 🔮 Future Enhancements

- Add collaborative filtering for personalized recs.
- Add genre/year filters.
- Include movie ratings & popularity scores.
- Allow multiple movie inputs for hybrid recs.

---

## 🧠 Author

- 🧑‍💻 **Aditya Inamdar**  

---

## 📜 License

MIT License
```

---
