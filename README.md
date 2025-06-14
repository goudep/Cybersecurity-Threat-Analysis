# Global Cybersecurity Threats Analysis (2015-2024)

## Project Overview

This is an end-to-end data analysis and machine learning project that explores global cybersecurity threat trends from 2015 to 2024. Using the Python data science stack, this project processes, analyzes, and visualizes a dataset of 3,000 cyber attack incidents to uncover patterns in attack types, targeted industries, financial losses, and security vulnerabilities.

The ultimate goal was to build a machine learning model to assess the feasibility of predicting attack types from high-level incident data, leading to key conclusions about the potential and limitations of AI in the cybersecurity domain.

**Tech Stack:** Python, Pandas, Matplotlib, Seaborn, Scikit-learn, Jupyter Notebook

---

## Dataset

* **Name:** Global Cybersecurity Threats (2015-2024)
* **Source:** [Kaggle Dataset Link](https://www.kaggle.com/datasets/teamincribo/global-cybersecurity-threats-2015-2024)
* **Description:** This dataset contains 3,000 simulated records of cybersecurity incidents, featuring dimensions such as country, year, attack type, target industry, financial loss, number of affected users, attack source, and defense mechanisms.

---

## Project Workflow & Findings

### 1. Data Cleaning and Preparation
* Loaded the dataset using Pandas and standardized all column names for consistency and ease of use (e.g., `Attack Type` -> `attack_type`).
* Verified the dataset's integrity, confirming there were no missing values and that all data types were appropriate for analysis.

### 2. Exploratory Data Analysis (EDA)
Using Matplotlib and Seaborn, data visualization led to several key findings:

* **Attack Type Distribution:** DDoS and Phishing were identified as the most frequent types of attacks.
* **Targeted Industries Analysis:** The IT sector was the primary target, followed by other critical sectors like Finance and Healthcare.
* **Attack Severity Analysis:**
    * **Frequency vs. Severity:** A critical insight was that high-frequency attacks (like DDoS) were not the most severe in terms of financial impact. Value-driven attacks like Ransomware caused the highest average **financial loss**.
    * **Impact Scope:** Attacks like Man-in-the-Middle and SQL Injection affected the largest **number of users**, revealing different dimensions of attack impact.
* **Time-Series Analysis:**
    * **Evolving Threat Landscape:** A clear upward trend was observed in the frequency of Ransomware and Phishing attacks in recent years.
    * **Financial Loss Trend:** The annual total financial loss correlated strongly with the rise of high-value attacks, indicating a shift towards "value-driven" cybercrime.

### 3. Machine Learning Modeling
* **Objective:** To build a classification model to predict the `attack_type` based on incident characteristics.
* **Feature Engineering:** Employed One-Hot Encoding to convert all categorical text features (e.g., `country`, `target_industry`) into a numerical format suitable for machine learning algorithms.
* **Model Selection:** Utilized a `RandomForestClassifier`, a powerful and robust ensemble model.
* **Model Evaluation:** Split the data into 80% training and 20% testing sets to evaluate the model's performance on unseen data.

---

## Conclusion & Reflection

1.  **Model Performance Revealed Data Limitations:**
    * The final model achieved an accuracy of approximately **17.2%**, only marginally better than random guessing (~16.7%). The detailed classification report confirmed poor precision and recall across all classes.
    * **Core Conclusion:** This result powerfully demonstrates that it is **not feasible** to build a reliable predictive model for attack types using only high-level, post-incident summary data.

2.  **Implications for AI in Cybersecurity:**
    * This project validates that effective cybersecurity AI systems require granular, real-time, low-level data (e.g., network packets, API call logs), not just high-level summaries.
    * Currently, AI serves best as a powerful **assistive tool** to augment human experts—for tasks like anomaly detection or automating responses—rather than fully replacing them in complex threat prevention and analysis.

While the model's predictive power was low, the project was a success in that it realistically demonstrated a critical principle in data science: **the quality and granularity of data determine the ceiling of a model's performance.**
