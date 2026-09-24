# 🎬 Recommender Systems: Latent Factors vs. Explicit Features

## 📋 Project Overview
This project explores and compares two fundamentally different approaches to building Recommender Systems: **Matrix Factorization (Collaborative Filtering)** and **Tree-based Supervised Learning**. 

Using two real-world datasets, the experiment compares a **Singular Value Decomposition (SVD)** model, which relies on learning latent user-item interaction patterns, against an **XGBoost Regressor**, which utilizes explicit feature engineering based on user demographics and item metadata.

The analysis is conducted entirely within a Jupyter Notebook, covering data preprocessing, hyperparameter optimization, model evaluation, and feature importance analysis.

---

## 🔬 Methodology & Models

### 1. SVD (Collaborative Filtering)
* **Approach:** Matrix Factorization.
* **Focus:** Analyzing the impact of the latent space dimensionality (`n_factors`).
* **Optimization:** Extensive Grid Search for hyperparameter tuning, specifically targeting learning rates (`lr_all`) and regularization terms (`reg_all`) to prevent overfitting.

### 2. XGBoost (Supervised Learning)
* **Approach:** Gradient Boosted Decision Trees for Regression.
* **Focus:** Feature Engineering. Instead of relying solely on interaction matrices, this model leverages explicit contextual data (e.g., User Age, User Occupation, Movie Genres).
* **Analysis:** Evaluating Feature Importance to understand which demographic or content-based variables drive user preferences the most.

---

## 📊 Datasets
The models are evaluated and benchmarked on two distinct datasets to observe behavior across different domains (Movies vs. Jokes):

1. **MovieLens 1M**
   * **Domain:** Cinema / Movies.
   * **Size:** ~1,000,000 ratings.
   * **Users & Items:** 6,040 users and 3,952 movies.
   * **Features used:** Ratings, User Demographics (Age, Gender, Occupation), Movie Genres.

2. **Jester 1**
   * **Domain:** Jokes / Humor.
   * **Size:** ~1.8 million continuous ratings (-10.00 to +10.00).
   * **Users & Items:** 24,983 users and 100 jokes.

---

## 📈 Evaluation Metrics
To ensure a robust comparison between the collaborative and content-based approaches, the following metrics were used:
* **RMSE (Root Mean Squared Error):** Primary metric, penalizing larger prediction errors.
* **MAE (Mean Absolute Error):** For an interpretable baseline of average error.
* **R² (Coefficient of Determination):** To measure the variance explained by the models.

*(Note: Detailed results, learning curves, and feature importance plots are documented directly inside the Jupyter Notebook).*

---

## ⚙️ Setup & Installation

To run the notebook and reproduce the experiments locally:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/N1c0zz/RecSys-SVD-vs-XGBoost.git
   cd RecSys-SVD-vs-XGBoost
   ```

2. **Create a virtual environment (Optional but recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

3. **Install the required dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```
   *Open the `.ipynb` file to view the analysis.*

---
*Developed by Nicolò Morini (nicomorini25@gmail.com)*
