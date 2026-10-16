# 🎬 The Movies – Data Analysis

What makes a film successful, both with audiences and at the box office?
This project analyzes [The Movies Dataset (TMDB, Kaggle)](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset/data) end to end: budget, revenue, genre, runtime and audience ratings. It also tests whether box office revenue can be predicted before release.

Built as part of the **Workintech Data Analyst Program**.

📄 **Presentation:** [The_Movies.pdf](./The_Movies.pdf) (in Turkish)

---

## 🛠 Tech Stack

| Step | Tool |
|---|---|
| Data warehouse | Google BigQuery |
| Transformation / data modeling | dbt |
| Statistical tests & machine learning | Python |
| Dashboard & presentation | Power BI |

## ❓ Hypotheses & Findings

**1. Does a bigger budget mean higher box office revenue?**
There's a strong positive correlation (~73%) between log budget and log revenue. However, about **30% of films lost money**, and the risk of a loss is highest in the mid-budget segment. A higher budget doesn't guarantee profit.

**2. Do average ratings differ by genre?**
Documentary, War and History get the highest average ratings, while Action and Adventure collect the most votes. Popularity ≠ quality.

**3. Does genre popularity change over time?**
Between 1950 and 2016, Documentary and Horror grew their share of production while Western and Crime declined. Even so, Crime and Horror generated high total profits after 1990.

**4. Does runtime affect ratings?**
Long films average **6.9** and short films **6.1**, and the difference holds across all 12 genres. Most long films are made by experienced directors.

## 🤖 Machine Learning – Predicting Box Office Revenue

- **Features:** budget, runtime, genre
- **Target:** log box office revenue
- **Models compared:** 5 (Linear Regression, tree-based models, tuned Gradient Boosting, …)
- **Best model:** Linear Regression with **R² = 0.523** on the test set
- **Key driver:** with other variables held constant, a 1% increase in budget is associated with a ~0.83% increase in expected revenue
- **Data quality note:** the largest errors are concentrated in 84 films with reported revenue under $10,000, so these records should be validated

## 📁 Repository Structure

```
├── The_Movies.pdf        # Power BI presentation (PDF export)
├── The_Movies.pbix       # Power BI report (optional)
├── models/               # dbt models (staging → mart)
├── notebooks/            # Python analyses & ML (optional)
└── README.md
```

## 👥 Team

- Gökberk Ozan
- Burak Gökçe
- Damla Eraslan
- Gülay Yıldırım

## 📚 Data Source

Rounak Banik, *The Movies Dataset*, Kaggle – metadata on 45,000+ films from TMDB and GroupLens (MovieLens).
The raw data isn't included in this repo because of its size; you can download it from the Kaggle link above.
