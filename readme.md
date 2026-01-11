# Customer Segmentation Using RFM Analysis

This project performs customer segmentation using Recency, Frequency, and Monetary (RFM) analysis to identify meaningful customer groups and support data-driven marketing, retention, and growth strategies.

---

## Objective

Segment customers based on purchasing behavior using RFM metrics so that businesses can:
- Identify high-value customers  
- Retain loyal customers  
- Re-engage at-risk customers  
- Optimize marketing efforts  

---

## Dataset

- Retail transaction dataset: `OnlineRetail.csv`  
- Key fields used:
  - CustomerID  
  - InvoiceDate  
  - InvoiceNo  
  - Quantity  
  - UnitPrice  

Cancelled transactions are retained to correctly compute net monetary value.

---

## Tech Stack

- Python  
- Pandas, NumPy  
- Scikit-learn  
- Matplotlib, Seaborn  

---

## Workflow

### 1. Data Cleaning
- Removed missing CustomerID  
- Converted InvoiceDate to datetime  
- Created TotalPrice = Quantity × UnitPrice  
- Preserved negative quantities for cancellation handling  

### 2. RFM Feature Engineering
For each customer:
- Recency: Days since last purchase  
- Frequency: Number of unique invoices  
- Monetary: Total net spending  

### 3. Transformation & Scaling
- Log transformation for Frequency and Monetary  
- Inverse transformation for Recency  
- Standardized using StandardScaler  

### 4. Cluster Selection
- Used Elbow Method  
- Used Silhouette Score  
- Selected k = 4  

### 5. Clustering
- Algorithm: K-Means  
- Customers assigned to one of four segments  

---

## Results

| Cluster | Behavior Summary |
|--------|------------------|
| 0 | Moderate activity, average value |
| 1 | Inactive, low value |
| 2 | Very recent, very frequent, very high value (Champions) |
| 3 | Recent, frequent, high value (Loyal) |

---

## Business Interpretation

### Champions  
- Very recent, very frequent, high spending  
- Action: VIP programs, early access  

### Loyal Customers  
- Frequent and recent buyers  
- Action: Cross-sell, loyalty rewards  

### Regular Customers  
- Moderate activity  
- Action: Upsell and promotions  

### At-Risk Customers  
- Long time since purchase, low activity  
- Action: Win-back campaigns  

---

## Visualization

- Elbow and Silhouette plots for cluster selection  
- Pairplots of RFM features colored by cluster to verify separation  

---

## Key Takeaways

- RFM clustering creates actionable customer segments  
- Data transformation improves clustering quality  
- Business interpretation is critical  
- Supports marketing, retention, and revenue growth  

---

## Files

- OnlineRetail.csv – Dataset  
- rfm_segmentation.ipynb – Main notebook  
- images/ – Visualizations  
