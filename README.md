import pandas as pd
import numpy as np

# Sample sales data for Excel dashboard
np.random.seed(42)
months = pd.date_range(start="2023-01-01", periods=12, freq="M").strftime("%b %Y")
categories = ["Electronics", "Clothing", "Grocery", "Furniture"]
data = {
    "Month": np.repeat(months, len(categories)),
    "Category": categories * len(months),
    "Sales_Amount": np.random.randint(20000, 150000, size=len(months) * len(categories)),
    "Units_Sold": np.random.randint(100, 1000, size=len(months) * len(categories))
}

sales_df = pd.DataFrame(data)
sales_df.head()
