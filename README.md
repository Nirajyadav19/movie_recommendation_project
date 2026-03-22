# 🎬 Movie Recommendation System

A content-based movie recommendation system built with Python and Streamlit that suggests similar movies based on your selection using cosine similarity on movie metadata.

---

## 📸 Demo

> 📌 **Add your Streamlit app screenshot here**
> Replace this section with: `<img width="1916" height="968" alt="image" src="https://github.com/user-attachments/assets/2a2636a5-052d-4069-8d87-58ea782aba93" />
)`

---

## 🚀 Features

- Recommends **5 similar movies** based on the selected movie
- Displays **movie posters** fetched from TMDB API
- Clean and interactive UI built with **Streamlit**
- Content-based filtering using **cosine similarity**

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Python 3.x |
| ML | Scikit-learn (CountVectorizer, Cosine Similarity) |
| UI | Streamlit |
| Data | TMDB Dataset |
| API | [TMDB API](https://www.themoviedb.org/documentation/api) |

---

## 📁 Project Structure

```
movie_recomandation_system/
│
├── app/                    # Streamlit app
│   └── app.py
│
├── src/                    # Source notebooks
│   ├── preprocessing.ipynb # Data cleaning & feature engineering
│   └── train.ipynb         # Model training & similarity matrix
│
├── data/
│   └── preprocessed.csv    # Cleaned dataset
│
├── artifacts/              # ⚠️ Not pushed to GitHub (in .gitignore)
│   ├── movie_list.pkl
│   └── similarity.pkl
│
├── requirements.txt
├── .gitignore
├── LICENSE
└── README.md
```

---

## ⚙️ How It Works

1. **Preprocessing** (`preprocessing.ipynb`): Cleans the TMDB dataset and engineers a `tags` column by combining genres, keywords, cast, crew, and overview.

2. **Training** (`train.ipynb`): Uses `CountVectorizer` (5000 features) to vectorize the tags, then computes a **cosine similarity matrix** across 4806 movies. The model artifacts are saved as `.pkl` files.

3. **App** (`app.py`): Loads the artifacts, takes a movie input, finds the top 5 most similar movies by similarity score, and fetches their posters from TMDB API.

---

## 🔧 Setup & Installation

### 1. Clone the repository
```bash
git clone https://github.com/your-username/movie_recomandation_system.git
cd movie_recomandation_system
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Generate the model artifacts
Run the notebooks in order:
```
1. preprocessing.ipynb  → generates data/preprocessed.csv
2. train.ipynb          → generates artifacts/movie_list.pkl & similarity.pkl
```

### 4. Run the app
```bash
streamlit run app/app.py
```

---

## 📦 Requirements

```
streamlit
scikit-learn
pandas
numpy
requests
pickle-mixin
```

---

## 📊 Dataset

- Source: [TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)
- Movies: **4806**
- Features used: title, genres, keywords, cast, crew, overview

---

## 📄 License

This project is licensed under the terms in the [LICENSE](LICENSE) file.
