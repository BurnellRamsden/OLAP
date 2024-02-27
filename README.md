import pandas as pd

# Create a sample DataFrame
data = {
    'Date': ['2022-01-01', '2022-01-02', '2022-01-03', '2022-01-04'],
    'Product': ['A', 'B', 'A', 'B'],
    'Sales': [100, 150, 120, 180]
}
df = pd.DataFrame(data)

# Perform OLAP operations using pandas
pivot_table = pd.pivot_table(df, values='Sales', index='Date', columns='Product', aggfunc='sum')
print("Pivot table:")
print(pivot_table)

# Perform additional OLAP operations
# For example, calculating total sales per day
total_sales_per_day = df.groupby('Date')['Sales'].sum()
print("\nTotal sales per day:")
print(total_sales_per_day)
