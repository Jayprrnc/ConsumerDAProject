# 📊 Customer Shopping Behavior Analysis (SQL + Python + MySQL)

## 📌 Project Overview
This project analyzes customer shopping behavior using **MySQL** and **Python (Pandas + SQLAlchemy)**.  
The goal is to extract **actionable business insights** related to customer demographics, purchasing patterns, discounts, subscriptions, shipping preferences, and product performance.

The dataset is ingested into MySQL using Python and analyzed using **advanced SQL techniques**, including **CTEs and window functions**.

---

## 🛠️ Tech Stack
- **Programming Language:** Python  
- **Database:** MySQL  
- **Libraries:** pandas, sqlalchemy, pymysql  
- **Tools:** VS Code, MySQL Workbench  

---

## 📂 Dataset Description
The dataset contains customer-level transactional data with the following columns:

| Column Name | Description |
|------------|------------|
| customer_id | Unique customer identifier |
| age | Customer age |
| gender | Gender |
| item_purchased | Product purchased |
| category | Product category |
| purchase_amount | Amount spent |
| location | Customer location |
| size | Product size |
| color | Product color |
| season | Purchase season |
| review_rating | Product rating |
| subscription_status | Subscriber or not |
| shipping_type | Shipping method |
| discount_applied | Discount applied |
| previous_purchases | Past purchases count |
| payment_method | Mode of payment |
| frequency_of_purchases | Purchase frequency |
| age_group | Age segmentation |
| purchase_frequency_days | Frequency in days |

---

## ⚙️ Data Loading (Python → MySQL)

```python
import pandas as pd
from sqlalchemy import create_engine
from urllib.parse import quote_plus

df = pd.read_csv('./Data/customer_shopping_behavior.csv')

engine = create_engine(
    "mysql+pymysql://root:Jay%401903@localhost:3306/customer_behavior"
)

df.to_sql("customer", engine, if_exists="replace", index=False)
