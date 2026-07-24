# Zomato Bangalore Restaurants – Seaborn Data Analysis & Visualization

📌 **Overview**

This repository contains a comprehensive Exploratory Data Analysis (EDA) and visualization project using the **Zomato Bangalore Restaurants** dataset from Kaggle. The analysis leverages Pandas, NumPy, and Seaborn to explore restaurant pricing strategies, customer preferences, and success patterns in Bangalore’s food-tech ecosystem.

The notebook walks through:
* **Real-world messy data cleaning:** Handling missing values, special characters, and type casting.
* **Feature engineering:** Creating business-centric metrics for actionable insights.
* **Categorical, distributional, and multivariate analysis:** Uncovering hidden patterns using modern data visualization techniques.
* **Advanced faceting and interaction effects:** Analyzing multi-variable relationships.
* **Strategic recommendations:** Data-driven takeaways for food delivery expansion.

---

## 🛠️ Tech Stack & Libraries Used

| Library | Primary Usage |
| :--- | :--- |
| **Pandas** | Data manipulation, cleaning, and transformation |
| **NumPy** | Numerical operations and array manipulation |
| **Seaborn** | Statistical data visualisations |
| **Matplotlib** | Customizing plots, axes, and formatting |
| **SciPy** | Skewness calculations and statistical probability checks |

---

## 📊 Key Sections & Visualizations Guide

### 1. Data Exploration & Cleaning
* **Q1–Q2:** Dataset inspection (`shape`, `dtypes`, missing values).
  * **Data Cleaning:** Removed duplicates and handled missing values in `rate` and `approx_cost(for two people)`.
  * **Type Conversion:** Cleaned string ratings (e.g., `"4.1/5"` $\rightarrow$ `4.1`) to `float`, and stripped commas from `approx_cost` to convert to `numeric`.
* **Q3 Feature Engineering:**

$$\text{cost\_per\_person} = \frac{\text{approx\_cost}}{2}$$

  * Binned ratings into categorical buckets (`Low`, `Medium`, `High`).

---

### 2. Categorical Analysis

#### Q4: Cost Distribution by Restaurant Type
Boxplot examining `cost_per_person` across `listed_in(type)` split by `online_order` status.
> **Insight:** Identifies premium vs. budget restaurant categories and highlights whether online ordering capability correlates with higher pricing.

#### Q5: Outlier Detection
Applied the Interquartile Range (IQR) method to identify extreme pricing outliers across different dining categories.

#### Q6: Rating Distribution Multi-Modality
Violin plot analyzing `rate` vs `listed_in(type)` to detect bi-modal or multi-modal rating distributions.

#### Q7: Swarmplot Rating Density
Detailed observation of rating density and dispersion across different restaurant types.

---

### 3. Business & Spatial Analysis

#### Q8: Mean vs. Median Ratings
Barplot contrasting `listed_in(type)` vs `rate` using both mean and median metrics.
> **Insight:** Demonstrates how extreme values and outliers skew the mean, making median a more reliable baseline for ratings.

#### Q9: Restaurant Concentration by Location
Countplot mapping restaurant density across Bangalore neighborhoods to identify key dining hubs.

#### Q10: Revenue Potential by Location
Barplot evaluating `location` vs `cost_per_person` to isolate high-ticket, premium dining zones.

---

### 4. Interaction Effects

#### Q11: Service Offering Interaction
Pointplot showcasing `online_order` vs `rate` faceted by table booking (`book_table`).
> **Insight:** Restaurants offering both table reservation and online delivery consistently score higher customer satisfaction ratings.

#### Q12: Spatial Pricing Dynamics
Advanced interaction plot evaluating `location` vs `cost_per_person` categorized by `listed_in(type)`.

---

### 5. Distribution Analysis

#### Q13: Binning Sensitivity in Histograms
Comparative study of `cost_per_person` using `bins=20` vs `bins=100` to illustrate oversmoothed vs overfitted noise.

#### Q14: Online Ordering Rating KDE
Kernel Density Estimate (KDE) plot showing rating distributions split by `online_order` availability.

#### Q15–Q17: Statistical Distribution & Probability
* Calculated dataset skewness for price metrics.
* **ECDF Plot:** Plotted the Empirical Cumulative Distribution Function to determine the percentage of restaurants costing under ₹500 per person.
* Calculated $P(\text{cost\_per\_person} > 1000)$ using cumulative density metrics.

---

### 6. Multivariate Analysis

#### Q18–Q19: Joint Pricing & Rating Distributions
* **2D Histogram & KDE Contour Plots:** Mapped joint distributions of `cost_per_person` against `rate` to uncover core price-to-quality density clusters.

---

### 7. Advanced Faceting

#### Q20: Multi-Factor Subplots
Catplot generating faceted boxplots across `online_order` and `book_table` parameters to understand cross-service pricing behavior.

---

### 8. Strategic Business Expansion

#### Q21: Expansion Strategy Recommendations
Data-backed business decision matrix for opening new delivery-first hubs:
* **Target Locations:** High-density neighborhoods with moderate average spending.
* **Pricing Strategy:** Position near the mid-range cost cluster (₹250–₹400/person).
* **Service Model:** Mandate online ordering integration from day one.

---

### 9. Modularized Pipeline

#### Q22: End-to-End Analysis Pipeline
Implemented a single, reusable Python function `analyze_restaurants(df)` that executes:
1. Automated data cleaning & type coercion.
2. Feature engineering pipeline.
3. Automated figure generation for key metrics.
4. Summary stat export for business decisions.

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone [https://github.com/your-username/zomato-bangalore-analysis.git](https://github.com/your-username/zomato-bangalore-analysis.git)
cd zomato-bangalore-analysis
