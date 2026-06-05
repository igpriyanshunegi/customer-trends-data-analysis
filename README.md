# 🛍️ Customer Shopping Behavior Analysis

> An end-to-end data analysis project exploring customer purchasing patterns, demographics, and spending habits using Python and Power BI.

---

## 📊 Dashboard Preview

<!-- Replace the link below with your actual screenshot URL -->
![Power BI Dashboard](https://github.com/igpriyanshunegi/-customer-trends-data-analysis/blob/main/Dashboard.png)


---

## 📁 Project Structure

```
customer-shopping-behavior-analysis/
│
├── 📓 Customer_shopping_behaviour_analysis.ipynb   # Main analysis notebook
├── 📄 customer_shopping_behavior.csv               # Raw dataset (3,900 records)
├── 📊 customer_behavior_dashboard.pbix             # Power BI dashboard file
├── 💡 Screenshot of dashboard
└── 📝 README.md
```

---

## 📌 About the Dataset

The dataset contains **3,900 customer records** with **18 features** capturing a wide range of shopping behavior attributes:

| Feature | Description |
|---|---|
| `Customer ID` | Unique identifier for each customer |
| `Age` | Customer age |
| `Gender` | Customer gender |
| `Item Purchased` | Name of the purchased item |
| `Category` | Product category (Clothing, Footwear, etc.) |
| `Purchase Amount (USD)` | Transaction value in USD |
| `Location` | US state of the customer |
| `Size` | Product size |
| `Color` | Product color |
| `Season` | Season of purchase |
| `Review Rating` | Customer rating (1–5) |
| `Subscription Status` | Whether customer has an active subscription |
| `Shipping Type` | Shipping method selected |
| `Discount Applied` | Whether a discount was used |
| `Promo Code Used` | Whether a promo code was applied |
| `Previous Purchases` | Number of past transactions |
| `Payment Method` | Payment method used |
| `Frequency of Purchases` | How often the customer shops |

---

## 🔬 Analysis Workflow

### 1. 📥 Data Loading & Exploration
- Loaded dataset using `pandas`
- Explored structure with `.head()`, `.info()`, and `.describe(include='all')`

### 2. 🧹 Data Cleaning
- Detected null values with `.isnull().sum()`
- Imputed missing `Review Rating` values using **category-wise median** to preserve statistical integrity
- Standardized all column names to **snake_case** for consistency

### 3. 🏗️ Feature Engineering
- Created **`age_group`** column using quartile binning (`pd.qcut`) with labels:
  - `Young Adult` · `Adult` · `Middle-aged` · `Senior`
- Created **`purchase_frequency_days`** by mapping text frequency labels to numeric day values:

  | Label | Days |
  |---|---|
  | Weekly | 7 |
  | Fortnightly / Bi-Weekly | 14 |
  | Monthly | 30 |
  | Quarterly / Every 3 Months | 90 |
  | Annually | 365 |

- Identified that `Discount Applied` and `Promo Code Used` were **100% identical** → dropped `promo_code_used` to eliminate redundancy

---

## 📈 Power BI Dashboard

The `.pbix` dashboard file provides interactive visualizations including:

- 🗺️ **Sales by Location** — geographic distribution of purchases
- 👥 **Customer Demographics** — age group and gender breakdown
- 🛒 **Purchase Patterns** — category and seasonal trends
- 💳 **Payment & Shipping Preferences** — method distribution
- ⭐ **Review Ratings** — average ratings across product categories
- 📅 **Purchase Frequency** — customer loyalty and engagement metrics

To open the dashboard, download [Power BI Desktop](https://powerbi.microsoft.com/desktop) and open `customer_behavior_dashboard.pbix`.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3 | Data analysis & feature engineering |
| pandas | Data manipulation |
| Jupyter Notebook | Interactive analysis environment |
| Power BI Desktop | Interactive dashboard & visualization |

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas jupyter
```

### Run the Notebook
```bash
git clone https://github.com/igpriyanshunegi/customer-trends-data-analysis.git
cd customer-shopping-behavior-analysis
jupyter notebook Customer_shopping_behaviour_analysis.ipynb
```

### Open the Dashboard
1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop)
2. Open `customer_behavior_dashboard.pbix`
3. Explore the interactive visualizations

---

## 💡 Key Insights

- **Seasonal trends** significantly influence product category preferences
- Customers with **active subscriptions** show higher average purchase values
- **Age group segmentation** reveals distinct purchasing patterns across demographics
- A majority of discounted purchases are concentrated in specific product categories


---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<p align="center">Made with ❤️ using Python & Power BI</p>
