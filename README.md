# Predictive-Analytics-Titanic-Pipeline
This is a comprehensive script. It covers the full lifecycle: **Data Cleaning, Feature Selection via Lasso, Pipeline Automation (the wrangle function), and Ensemble Learning.**

To make your GitHub repository stand out, the README should emphasize the **why** behind your technical choices (like using Lasso to justify dropping `SibSp` and `Parch`).

Here is a professional `README.md` structure for your repository.

-----

# Titanic Survival Prediction: A Multi-Stage Ensemble Approach

[](https://www.python.org/)
[](https://scikit-learn.org/)

## 📌 Project Overview

This project predicts passenger survival on the Titanic by moving beyond simple classification. It utilizes **Lasso Regression** for objective feature selection and a **Voting Classifier (Ensemble)** to combine the strengths of linear, distance-based, and tree-based models.

## 🛠️ Technical Workflow

### 1\. Advanced Data Wrangling

Instead of simple deletion, I built a robust `wrangle` function to handle the data pipeline consistently across training and testing sets:

  * **Custom Imputation:** Imputed `Age` based on the median of the `Pclass` groups (First Class: 38, Second: 29, Third: 24) to maintain demographic accuracy.
  * **Missingness Analysis:** Used `missingno` to visualize data gaps and `SimpleImputer` for final cleanup.
  * **Encoding:** Implemented `OneHotEncoder` for categorical variables (`Sex`, `Embarked`).

### 2\. Feature Engineering & Selection

I used **Lasso Regression** to mathematically determine which variables truly impacted survival.

  * **Key Discovery:** The model identified that `SibSp` (siblings/spouses) and `Parch` (parents/children) had negligible coefficients.
  * **Action:** Dropped non-impactful features to reduce model noise and prevent overfitting.

### 3\. The Ensemble Strategy

Rather than relying on one algorithm, I implemented a **Voting Classifier** to combine:

  * **Logistic Regression:** To capture linear trends.
  * **Decision Tree:** To capture non-linear interactions.
  * **K-Nearest Neighbors (KNN):** To identify clusters of similar passenger profiles.

## 📈 Results & Insights

  * **The Class Gap:** Passengers in 1st Class had a survival rate of **63%**, compared to just **24%** for 3rd Class.
  * **Gender Bias:** Despite fewer females on board, the "women and children first" protocol resulted in significantly higher female survival counts.
  * **Model Strength:** The ensemble approach produced a more generalized prediction by mitigating the individual biases of each classifier.

## 🚀 How to Run

1.  Clone the repository:
    ```bash
    git clone https://github.com/ChijiokeAmanze/Titanic-Survival-Ensemble-Modeling.git
    ```
2.  Install dependencies:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn missingno
    ```
3.  Run the script/notebook to generate the `titanic_submission.csv`.

## 🧰 Tools Used

  * **Languages:** Python
  * **Libraries:** Pandas, NumPy, Scikit-Learn
  * **Visualization:** Seaborn, Matplotlib, Missingno

-----

### Final Polish Tips for your Repo:

1.  **Add a "Visuals" folder:** Upload those 3 charts we discussed earlier (the boxplot, histogram, and countplot) and reference them in the README using `![Title](path/to/image.png)`.
2.  **File Structure:** List your files in the README so recruiters know where to look:
      * `main.py` / `notebook.ipynb`: Core logic.
      * `wrangle_function.py`: Modularized cleaning script.
      * `data/`: Training and testing CSVs.
3.  **The "So What":** I added a line in the Ensemble section about **generalization**. This is a keyword recruiters love because it shows you care about how the model performs on *real* data, not just training data.

**Would you like me to help you write the `requirements.txt` file so others can install your project environment with one command?**
