# 🛍️ Customer Segmentation Using RFM and K-Means Clustering

## 📘 Project Overview
This project applies **unsupervised learning** to segment retail customers based on purchasing behaviour.  
Using **Recency, Frequency, and Monetary (RFM)** metrics derived from transactional data, the goal is to help retailers understand and target customer groups more effectively — driving retention, loyalty, and sales growth.

---

## 🎯 Problem Statement
Retailers often treat all customers the same, missing opportunities to tailor offers or engagement strategies.  
This project aims to identify **distinct customer groups** based on how recently, how often, and how much they purchase.  
By uncovering these segments, the business can:
- Reward loyal and high-value customers  
- Re-engage at-risk customers  
- Personalize marketing strategies  
- Optimize budget and improve ROI  

---

## 📂 Dataset Information
**Dataset:** [Retail Sales Dataset – Kaggle](https://www.kaggle.com/datasets/mohammadtalib786/retail-sales-dataset)

**Columns Used**
- `Customer ID` — unique identifier for each customer  
- `Order ID` — unique transaction identifier  
- `Order Date` — date of purchase  
- `Quantity` — number of items bought  
- `Unit Price` — price per item  
- `Amount` — total price per transaction  

**Why this dataset:**  
It contains key behavioural variables needed to compute RFM metrics and is clean, structured, and representative of a real retail business scenario.

---

## 🧮 Methodology

### 1️⃣ Data Preparation
- Loaded and cleaned retail sales data.  
- Removed duplicates, negative quantities, and invalid entries.  
- Parsed order dates and ensured numerical consistency.

### 2️⃣ Feature Engineering (RFM)
Computed three key customer metrics:
- **Recency** → Days since last purchase  
- **Frequency** → Number of unique orders  
- **Monetary** → Total spending value  

3️⃣ Data Transformation

Applied log transformation on Monetary to reduce skew.

Scaled RFM features using RobustScaler (less sensitive to outliers).

4️⃣ Finding Optimal K

Tested cluster numbers (k = 2–8) using:

Elbow Method → Finds the point where inertia reduction slows (the “elbow”).

Silhouette Score → Measures how distinct and compact clusters are.

5️⃣ Final Modelling

Applied K-Means with the best k (based on Silhouette).

Assigned each customer to a segment.

6️⃣ Segment Profiling

Calculated averages per cluster:

Metric	Meaning	Desired Trend

Recency	Days since last purchase	Lower is better

Frequency	Number of orders	Higher is better

Monetary	Total spend: Higher is better


7️⃣ Persona Labelling

Automatically ranked and labelled clusters:

🏆 Champions – recent, frequent, high spenders

❤️ Loyal – frequent buyers, moderate spenders

🌱 Promising – newer or moderate buyers

⚠️ At Risk – infrequent, haven’t purchased recently

❄️ Hibernating – old, inactive customers

📊 Key Insights

High-value “Champions” make up a small portion of customers but drive a large share of revenue.

“At Risk” and “Hibernating” customers highlight opportunities for win-back campaigns.

Simple, data-driven segmentation enables targeted promotions and loyalty programs.

🚀 Tools & Libraries

Python 3.10+

Pandas, NumPy — data wrangling

Matplotlib, Seaborn — visualisation

Scikit-learn — scaling, clustering, evaluation




🏁 Results & Impact

Produced clear customer segments with interpretable patterns.

Provides actionable business insights for personalized marketing.

Demonstrates applied mastery of data cleaning, feature engineering, clustering, and model interpretation.

👥 Author

Simeon Musa Nyakeh Vibbi
AI Saturdays Lagos — Machine Learning Flipped Cohort
📧 svibbinyakeh@gmail.com
🔗 [[Your LinkedIn ](https://www.linkedin.com/in/simeon-nyakeh-vibbi-a7992b178/)/ [GitHub Profile](https://github.com/SNVibbi)

🧾 Acknowledgment

Special thanks to AI Saturdays Lagos mentors and peers for guidance throughout the ML Flipped Cohort.
Dataset credit: Mohammad Talib – Kaggle
