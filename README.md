# Discovering Hidden Personality Patterns using Unsupervised Learning

---

## Project Overview

This project is the final assignment for an Unsupervised Machine Learning course. The goal is to apply **Principal Component Analysis (PCA)** and **K-Means clustering** to a large dataset of personality test responses to identify natural, hidden personality clusters. The objective is to understand how individuals group based on the **Big Five personality traits** without relying on predefined labels.

---

## The Big Five Personality Model (OCEAN)

The Big Five personality traits (or Five-Factor Model, FFM) are used for grouping different personality dimensions. The five core traits analyzed in this project are:

* **O** - **Openness to Experience**: Curiosity, creativity, inventiveness
* **C** - **Conscientiousness**: Organization, responsibility, efficiency
* **E** - **Extraversion**: Sociability, assertiveness, outgoing nature
* **A** - **Agreeableness**: Kindness, cooperation, compassion
* **N** - **Neuroticism**: Emotional instability, sensitivity, nervousness

---

## Dataset

The analysis uses the **Big Five Personality Test** dataset sourced from Kaggle.

* **Source:** Questionnaire answers collected online by Open Psychometrics.
* **Scale:** The response scale was labeled: **1 = Disagree**, **3 = Neutral**, **5 = Agree**.
* **Size:** The raw dataset contains over 1 million questionnaire answers (1,015,342 initial entries).

---

## Methodology and Steps

The project follows a standard machine learning workflow, focusing heavily on data preparation and unsupervised modeling:

### 1. Data Preparation and Cleaning
* **Loading:** The raw data was loaded from the `data-final.csv` file.
* **Feature Selection:** Irrelevant columns, such as time spent on each question (`_E` variables) and technical demographic data, were dropped.
* **Missing Values:** Rows with any missing values were removed, resulting in a clean dataset of over 1 million participants.

### 2. Data Preprocessing
* **Scaling:** The numeric features were scaled to a range of [0, 1] using **MinMaxScaler** to prevent variables with larger magnitudes from dominating the analysis.

### 3. Dimensionality Reduction (PCA)
* **Objective:** To reduce the 50 original question features while retaining the maximum variance, allowing for easier visualization and more efficient clustering.
* **Selection:** The optimal number of principal components was determined (e.g., using an elbow plot on the explained variance).

### 4. Clustering (K-Means)
* **Determining K:** The **Elbow Method** and **Silhouette Score** were used to find the optimal number of clusters (`k`) in the reduced feature space.
* **Clustering:** The **K-Means algorithm** was applied with the chosen `k` to segment the participants.

### 5. Results and Interpretation
* The final step involved analyzing the characteristics of the centroids for each identified cluster to assign meaningful **personality profiles** to each group.
* Cluster sizes and distribution were analyzed and visualized using a bar plot to ensure a balanced clustering result.

---

## Technologies and Libraries

This project was developed using Python and the following key libraries:

* **pandas** and **numpy** for data manipulation.
* **matplotlib** and **seaborn** for visualization and Exploratory Data Analysis (EDA).
* **sklearn** (Scikit-learn) for machine learning components:
    * `MinMaxScaler` (Preprocessing)
    * `PCA` (Dimensionality Reduction)
    * `KMeans` (Clustering)
    * `silhouette_score` (Evaluation)
