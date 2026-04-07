# 🎯 Anime Recommendation System using Content-Based Filtering

## 📌 Problem Statement

The goal of this project is to build a recommendation system that suggests similar anime to users based on features such as genre, rating, episodes, and popularity.

---

## 📊 Dataset

* Dataset used: **Anime Dataset (anime.csv)**
* Contains information like:

  * Name
  * Genre
  * Type
  * Episodes
  * Rating
  * Members (popularity)

---

## ⚙️ Approach

### 1. Data Preprocessing

* Handled missing values:

  * Dropped missing categorical values (`genre`, `type`)
  * Filled missing `rating` using median
* Converted `episodes` to numeric
* Reset index after cleaning

### 2. Feature Engineering

* Split multiple genres into dummy variables (one-hot encoding)
* Scaled numeric features (`episodes`, `rating`, `members`) using **MinMaxScaler**

### 3. Similarity Calculation

* Used **Cosine Similarity** to measure similarity between anime
* Created a similarity matrix for all anime items

### 4. Recommendation Logic

* Built a function to:

  * Find similarity scores for a given anime
  * Sort them in descending order
  * Recommend top similar anime

### 5. Threshold-Based Filtering

* Implemented a threshold-based recommendation system
* Only recommends anime with similarity above a chosen threshold

---

## 📈 Results

* Generated recommendations for popular anime like:

  * Naruto
  * Death Note
  * Kimi no Na wa

* Threshold tuning results:

  * Threshold = 0.8 → Highly relevant but fewer recommendations
  * Threshold = 0.6 → Balanced recommendations
  * Threshold = 0.4 → More recommendations but lower relevance

Example:

* At threshold **0.4**, system generated a larger number of recommendations compared to higher thresholds.

---

## 🔍 Key Insights

* Cosine similarity works effectively for high-dimensional feature data
* Feature engineering (genre splitting) significantly improves recommendation quality
* Threshold tuning is critical:

  * Higher threshold → more accurate but fewer results
  * Lower threshold → more results but less precise

---

## 🚀 Future Improvements

* Use collaborative filtering (user-based or item-based)
* Implement hybrid recommendation system
* Add user ratings for personalized recommendations
* Deploy as a web application

---

## 🛠️ Technologies Used

* Python
* Pandas, NumPy
* Scikit-learn
* Matplotlib, Seaborn

---

## 📌 Conclusion

This project demonstrates how content-based recommendation systems work using similarity measures. It highlights the importance of preprocessing, feature engineering, and threshold tuning in building effective recommendation engines.
