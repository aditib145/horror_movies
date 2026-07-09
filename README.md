# horror_movies
Analyzing horror movie trends across decades and predicting box office revenue using a Random Forest model, built on a 32K+ movie TMDB dataset with an interactive revenue predictor.
# 🎬 Horror Movies Analysis & Revenue Prediction

An end-to-end data science project analyzing the evolution of horror movies over the decades and building a machine learning model to predict box office revenue — complete with an interactive predictor.

---

## 📌 Project Overview

This project explores a Kaggle dataset of horror movies (sourced from TMDB) to uncover trends in ratings, popularity, and runtime across decades, and builds a **Random Forest Regression model** to predict a horror movie's revenue based on features like budget, popularity, and audience rating.

**Key question explored:** *Can we predict how much a horror movie will earn, just from its budget, popularity, and ratings?*

---

## 📊 Dataset

- **Source:** [Kaggle - TMDB Horror Movies Dataset]
- **Size:** 32,540 movies × 20 columns
- **Key columns used:** `budget`, `revenue`, `popularity`, `vote_average`, `vote_count`, `runtime`, `genre_names`, `release_date`

---

## 🧹 Data Cleaning

- Handled missing values in `overview`, `tagline`, and `collection_name` columns
- Identified that `budget` and `revenue` had a large number of `0` values (unknown/unreported data) — filtered these out for financial analysis, creating a clean subset (`finance_df`) of movies with valid budget and revenue
- Extracted `year` and `decade` from `release_date` for trend analysis

---

## 📈 Exploratory Analysis: Horror Movies Through the Decades

Analyzed how horror movies have evolved decade by decade across four dimensions:

- **Movie Count per Decade** — volume of horror movies released over time
- **Average Rating per Decade** — how audience reception has shifted
- **Average Popularity per Decade** — trend in popularity scores
- **Average Runtime per Decade** — how movie length has changed

*(Insert decade-wise trend chart screenshot here)*

**Key Insight:** *(Fill in your own observation, e.g., "Horror movie output surged post-2000s, while average ratings remained relatively stable across decades.")*

---

## 🤖 Revenue Prediction Model

Built a **Random Forest Regressor** to predict movie revenue using:

- `log_budget` (log-transformed for skew correction)
- `popularity`
- `vote_average`
- `vote_count`
- `runtime`
- `genre_count`

Revenue was also log-transformed (`log_revenue`) to handle the heavy right-skew typical of box office data.

### Model Performance
| Metric | Score |
|--------|-------|
| R² Score | **0.77** |
| MAE (log scale) | 1.29 |

*(Insert feature importance chart screenshot here)*

**Key Insight:** Budget emerged as the strongest predictor of revenue, followed by popularity and vote count — suggesting that both production investment and audience buzz play major roles in a horror movie's box office success.

---

## 🎛️ Interactive Revenue Predictor

Built an interactive widget (using `ipywidgets`) directly inside the notebook, allowing users to adjust budget, popularity, rating, vote count, runtime, and genre count via sliders and instantly see:
- Predicted revenue
- Estimated profit or loss

<img width="507" height="277" alt="image" src="https://github.com/user-attachments/assets/358ab310-a5c6-49d4-9a50-2cb44953efcd" />


---

## 🛠️ Tech Stack

- **Language:** Python
- **Libraries:** pandas, numpy, matplotlib, seaborn, scikit-learn, ipywidgets
- **Environment:** Jupyter Notebook

---

## 🚀 How to Run

1. Clone this repository
   ```bash
   git clone https://github.com/aditib145/<repo-name>.git
   cd <repo-name>
   ```
2. Install dependencies
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn ipywidgets
   ```
3. Download the dataset from Kaggle and place it in the project folder
4. Open and run the notebook
   ```bash
   jupyter notebook horror_movies_analysis.ipynb
   ```

---

## 📂 Repository Structure

```
├── horror_movies_analysis.ipynb   # Main analysis & model notebook
├── README.md                      # Project documentation
└── images/                        # Visualization screenshots
```

---

## 👤 Author

**Aditi Bhardwaj**
- GitHub: [@aditib145](https://github.com/aditib145)
- Kaggle: [aditib145/aditi501](https://www.kaggle.com/aditib145)
- linkedin: https://www.linkedin.com/in/aditi-bhardwaj-b4b52b33b/?lipi=urn%3Ali%3Apage%3Ad_flagship3_leia_creator_analytics_content%3B79FzNOOVTauW8NzH8HJGwQ%3D%3D

---

## 🔮 Future Improvements

- Add genre-wise revenue comparison within horror sub-genres (slasher, supernatural, psychological, etc.)
- Try additional models (XGBoost, Gradient Boosting) for improved accuracy
- Deploy the predictor as a Streamlit web app for wider accessibility
