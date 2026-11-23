# 🛍️ Customer Segmentation using K-Means Clustering

A machine learning project that segments mall customers into distinct groups based on their **Annual Income** and **Spending Score**, using the **K-Means Clustering** algorithm. This kind of segmentation helps businesses target the right customers with the right strategies.

---

## 📌 Overview

Understanding customer behavior is critical for any retail business. Instead of treating all customers the same, this project identifies natural groupings within the customer base — allowing for personalized marketing, better resource allocation, and improved customer experience.

This is an **unsupervised learning** problem since there are no predefined labels — the model discovers the structure in the data on its own.

---

## 🧠 Model

| Detail | Value |
|---|---|
| Algorithm | K-Means Clustering |
| Initialization | K-Means++ |
| Optimal Clusters | 5 (determined via Elbow Method) |
| Features Used | Annual Income, Spending Score |
| Random State | 0 |

---

## 📂 Dataset

**Mall Customers Dataset** (`Mall_Customers.csv`)

| Feature | Description |
|---|---|
| `CustomerID` | Unique ID for each customer |
| `Gender` | Male / Female (encoded: Male→1, Female→0) |
| `Age` | Age of the customer |
| `Annual Income (k$)` | Annual income in thousands of dollars |
| `Spending Score (1-100)` | Score assigned by the mall based on spending behavior |

> The model uses only **Annual Income** and **Spending Score** as clustering features.

---

## ⚙️ Workflow

```
Raw Dataset (Mall_Customers.csv)
    │
    ▼
Data Loading & Exploration      → Shape, null check, basic stats
    │
    ▼
Preprocessing                   → Gender encoding (Male→1, Female→0)
    │
    ▼
Feature Selection               → Annual Income + Spending Score
    │
    ▼
Elbow Method                    → WCSS for k=1 to 10 → Optimal k=5
    │
    ▼
K-Means Training                → Fit model with 5 clusters
    │
    ▼
Cluster Visualization           → Scatter plot with centroids
```

---

## 📊 Customer Segments Identified

| Cluster | Annual Income | Spending Score | Profile |
|---|---|---|---|
| 1 | Low | Low | Budget-conscious, low spenders |
| 2 | Low | High | Low income but high spenders |
| 3 | Medium | Medium | Average customers |
| 4 | High | Low | High earners, cautious spenders |
| 5 | High | High | Premium customers — top priority |

> ℹ️ Cluster labels above are interpreted from the scatter plot. Adjust based on your actual output.

---

## 📈 Elbow Method

The **Within-Cluster Sum of Squares (WCSS)** was calculated for k = 1 to 10. The elbow point at **k = 5** indicates the optimal number of clusters — beyond this, adding more clusters gives diminishing returns.

---

## 🛠️ Tech Stack

- **Python 3**
- **NumPy** — numerical operations
- **Pandas** — data manipulation
- **Matplotlib** — cluster visualization
- **Seaborn** — elbow graph styling
- **Scikit-learn** — K-Means clustering

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/your-username/customer-segmentation-kmeans.git
cd customer-segmentation-kmeans
```

### 2. Install dependencies
```bash
pip install numpy pandas matplotlib seaborn scikit-learn
```

### 3. Add the dataset
Place `Mall_Customers.csv` in the project folder and update the path in the notebook:
```python
customer_data = pd.read_csv('Mall_Customers.csv')
```

### 4. Run the notebook
Open `Customer-Segmentation.ipynb` in Jupyter Notebook or Google Colab and run all cells.

---

## 📁 Project Structure

```
customer-segmentation-kmeans/
│
├── Customer-Segmentation.ipynb    # Main notebook
├── Mall_Customers.csv             # Dataset (add manually)
├── README.md                      # Project documentation
└── .gitignore                     # Files to ignore in git
```

---

## 🔮 Future Improvements

- Use all features (Age, Gender, Income, Score) with dimensionality reduction (PCA) for richer clustering
- Try other clustering algorithms like DBSCAN or Hierarchical Clustering and compare
- Add silhouette score analysis for better cluster validation
- Build an interactive dashboard using Streamlit for business users
- Deploy as an API endpoint for real-time customer classification

---

