# Experiment 1.B: Product Price Analysis Using Python Functions

## Aim

To analyze quarterly product sales data across multiple products and quarters using 2D NumPy arrays and Python statistical functions.

## Algorithm

1. **Start** the program.
2. **Import Library**: Import the `numpy` module as `np` for numerical array operations.
3. **Initialize 2D Sales Matrix**: Create a 3 × 4 NumPy array `sales` containing quarterly sales figures for 3 products across 4 quarters.
4. **Compute Product-Wise Totals**: Calculate the sum of sales across columns (`axis=1`) for each product using `np.sum(sales, axis=1)`.
5. **Compute Quarter-Wise Totals**: Calculate the sum of sales across rows (`axis=0`) for each quarter using `np.sum(sales, axis=0)`.
6. **Compute Overall Statistical Metrics**:
   * Calculate the overall mean sales across all entries using `np.mean(sales)`.
   * Identify the maximum sales figure using `np.max(sales)`.
   * Identify the minimum sales figure using `np.min(sales)`.
7. **Display Analysis Summary**: Print the original sales matrix, product-wise totals, quarter-wise totals, overall average, highest sale, and lowest sale.
8. **Stop** the program.

## Program

```python
import numpy as np

# Step 1: Create 2D array (Rows = Products, Columns = Quarters)
sales = np.array([
    [12000, 15000, 14000, 18000],   # Product 1
    [20000, 22000, 19000, 25000],   # Product 2
    [8000,  9500,  10000, 11000]    # Product 3
])

# Step 2: Calculate Aggregations and Summary Statistics
product_totals = np.sum(sales, axis=1)    # Sum across quarters for each product
quarter_totals = np.sum(sales, axis=0)    # Sum across products for each quarter
overall_mean = np.mean(sales)
highest_sale = np.max(sales)
lowest_sale = np.min(sales)

# Step 3: Display Summary
print("Quarterly Sales Matrix (Rows = Products, Columns = Quarters):")
print(sales)

print("\nProduct-wise Total Sales:")
for i, total in enumerate(product_totals, start=1):
    print(f"  Product {i}: {total}")

print("\nQuarter-wise Total Sales:")
for i, total in enumerate(quarter_totals, start=1):
    print(f"  Q{i}: {total}")

print(f"\nOverall Average Sales : {overall_mean:.2f}")
print(f"Highest Sale          : {highest_sale}")
print(f"Lowest Sale           : {lowest_sale}")
```

## Output

```
Quarterly Sales Matrix (Rows = Products, Columns = Quarters):
[[12000 15000 14000 18000]
 [20000 22000 19000 25000]
 [ 8000  9500 10000 11000]]

Product-wise Total Sales:
  Product 1: 59000
  Product 2: 86000
  Product 3: 38500

Quarter-wise Total Sales:
  Q1: 40000
  Q2: 46500
  Q3: 43000
  Q4: 54000

Overall Average Sales : 15291.67
Highest Sale          : 25000
Lowest Sale           : 8000
```

## Result

The program successfully analyzes quarterly product sales using 2D NumPy arrays and Python statistical aggregation functions.
