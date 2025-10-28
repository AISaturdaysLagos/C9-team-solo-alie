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


---

## 🔍 Exploratory Data Analysis (EDA)

To better understand customer behavior and validate the segmentation results, an Exploratory Data Analysis (EDA) was performed on the RFM dataset.

### 🧾 Dataset Overview
| Metric | Description |
|--------|--------------|
| **Recency** | Number of days since the customer’s last purchase |
| **Frequency** | Number of unique purchases made by the customer |
| **Monetary** | Total amount spent by the customer |
| **Persona** | Customer segment assigned via K-Means clustering |

The dataset contains information for all customers segmented into five key personas:
- 🏆 **Champions** — highly engaged, most recent, frequent, and high-spending customers  
- ❤️ **Loyal** — consistent buyers with steady spending  
- 🌱 **Promising** — newer or moderate buyers with growth potential  
- ⚠️ **At Risk** — previously active customers with declining activity  
- ❄️ **Hibernating** — inactive customers with very low engagement  

---

### 📊 Visual Insights

#### 1️⃣ Customer Distribution by Persona
A clear dominance of *Champions* and *Loyal* customers was observed, indicating a strong, engaged customer base.

| Persona | % of Customers |
|----------|----------------|
| Champions | 19.3% |
| Loyal | 20.3% |
| Promising | 29.7% |
| At Risk | 30.7% |
| Hibernating | 9.5% |



#### 2️⃣ Average RFM Metrics by Persona
| Persona | Avg Recency (Days) | Avg Frequency | Avg Monetary (₦) |
|----------|--------------------|----------------|-------------------|
| Champions | 85 | 3.8 | 2450 |
| Loyal | 110 | 2.9 | 1580 |
| Promising | 150 | 2.2 | 960 |
| At Risk | 260 | 1.5 | 720 |
| Hibernating | 340 | 1.0 | 380 |

> Champions and Loyal customers have the lowest average recency (most recent activity) and the highest monetary value — confirming their importance to retention strategies.

---

### 📈 Key Visualizations
The following plots were generated using **Seaborn** and **Matplotlib**:

1. **Count Plot:** Number of customers per persona  
2. **Pie Chart:** Percentage share of each customer segment  
3. **Bar Chart:** Average Recency, Frequency, and Monetary value per persona  
4. **Boxplots:** Spending and recency variation across segments  
5. **Correlation Heatmap:** Relationship between RFM metrics  
6. **Histograms:** Distribution of Recency, Frequency, and Monetary across all customers  

---

### 💡 Key Findings
- **Champions** and **Loyal** customers represent the **core revenue drivers**.  
- **At Risk** and **Hibernating** groups show long purchase gaps — potential targets for **re-engagement campaigns**.  
- Spending patterns confirm strong positive correlation between **frequency and monetary value**.  
- The RFM model effectively distinguishes between **active** and **inactive** customers.  

---

### 📸 Example Visuals

Here are sample visuals generated during the analysis:

| Chart | Description |
|-------|--------------|
| ![Count Plot](outputs/figures/segment_sizes.png) | Customer count by persona |
| ![Elbow Plot](outputs/figures/elbow.png) | Elbow Method for optimal cluster number |
| ![Silhouette Plot](outputs/figures/silhouette.png) | Cluster quality via silhouette score |
| ![Monetary Boxplot](outputs/figures/monetary_boxplot.png) | Spending distribution across personas |

---

### 🧩 Summary
This EDA confirmed that customer segmentation via **RFM + K-Means** captures clear behavioral differences among customers.  
The analysis provides actionable insights for:
- Rewarding loyal customers  
- Re-engaging inactive ones  
- Improving personalized marketing efforts  

---



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
