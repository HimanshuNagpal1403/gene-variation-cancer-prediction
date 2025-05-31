# Cancer Prediction Using Machine Learning

This project predicts cancer types using machine learning by combining structured gene mutation data with unstructured clinical text. The model classifies cancer types based on genetic mutations and associated clinical information. It involves feature engineering, text vectorization (TF-IDF), and classification models.

## 🧠 Project Overview

The goal of this project is to build a machine learning model that can predict cancer types based on:

- **Gene**: The gene involved in the mutation
- **Variation**: The specific mutation that occurred
- **Text**: Clinical and biological background for each mutation

This project is based on the data from the Kaggle competition [MSK: Redefining Cancer Treatment](https://www.kaggle.com/competitions/msk-redefining-cancer-treatment/data). The solution explores data preprocessing, feature engineering, and training machine learning models to classify cancer types.

---

## 📁 Project Structure
```bash
|--main
|   |──> solution.ipynb # Main Jupyter Notebook (Solution)
|   |──> training_variants.csv # Gene and Variation data
|   |──> training_text.csv # Clinical text data


- **solution.ipynb**: The main notebook where all data preprocessing, feature engineering, model building, and evaluation are done.
- **training_variants.csv**: Contains gene mutation data (Gene, Variation, ID).
- **training_text.csv**: Contains clinical background text for each mutation ID.
```

---

## 🔍 Data Description

The dataset contains the following files:

- `training_variants.csv`: Contains columns like `ID`, `Gene`, `Variation`, and other mutation-related features.
- `training_text.csv`: Contains columns like `ID` and `Text`, which is the clinical description of each mutation.

### Source of Data:
The data for this project was taken from the Kaggle competition [MSK: Redefining Cancer Treatment](https://www.kaggle.com/competitions/msk-redefining-cancer-treatment/data).

---

## 🧪 Approach

1. **Data Merging and Cleaning**
   - Performed a left join between gene-variation and clinical text data using the `ID`.
   - Filled missing `Text` fields with a combination of `<Gene> + <Variation>` to prevent data loss.

2. **Text Preprocessing**
   - Lowercased text, removed punctuation.
   - Tokenized and removed stop words.
   - Applied TF-IDF vectorization to convert text into numerical features.

3. **Feature Engineering**
   - Combined TF-IDF vectors with one-hot encoded `Gene` and `Variation` features.

4. **Modeling**
   - Applied Logistic Regression and other classifiers (e.g., Random Forest, Naive Bayes).
   - Used cross-validation to evaluate model performance.

5. **Evaluation**
   - Accuracy, Precision, Recall, and F1 Score were calculated.
   - A confusion matrix was visualized to better understand misclassifications.

---

## 🤖 Models Used

- Logistic Regression
- Random Forest (optional)
- Naive Bayes (optional)
