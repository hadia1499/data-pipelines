# Assignment 1: Data Pipelines with Databricks

![pipeline](pipeline.gif)

**By:** Hadia Asif

I loaded Microsoft's **AdventureWorks2022** data into Databricks, built a small **star schema**, and checked it with SQL.

## What I did in each exercise

**Exercise 1: Load the data**
Downloaded 3 CSV files from Microsoft's GitHub, created the catalog `Adventure_Works` and the volume `raw_data`, and uploaded the files.

**Exercise 2: Add column names**
The CSVs had no headers and were tab-separated. I took the column names from `instawdb.sql` and saved 3 Delta tables: `fact_sales`, `dim_product`, `dim_sales_territory`.

**Exercise 3: Explore the workspace**
Learned what Workspace, Catalog, Compute, Jobs and Data Ingestion are for. Checked the columns with `DESCRIBE` and counted rows.

**Exercise 4: Verify the star schema**
Every `SalesOrderDetailID` is unique. LEFT JOIN kept 121,317 rows, so no fan-out. RIGHT JOIN added 238 rows for products that were never sold. No duplicate keys.

**Exercise 5: First SQL queries**
Found the top revenue products, checked for NULL or negative values (none), and made a bar chart of the top 5.

**Exercise 6: Data profiling**
No orphan sales. 238 products never sold. Water Bottle is ordered most often, but Road and Mountain bikes bring the most revenue.

**Exercise 6: GitHub**
Created this repo and uploaded a Hello World notebook and my Lesson 1 notebook.

## Tables
| Table | Source | Rows |
|---|---|---|
| `fact_sales` | SalesOrderDetail.csv | 121,317 |
| `dim_product` | Product.csv | 504 |
| `dim_sales_territory` | SalesTerritory.csv | 10 |

**Note:** `fact_sales` has no `TerritoryID` (it is in `SalesOrderHeader`), so it can't be joined to `dim_sales_territory` directly yet.

## Files
- `hello_world.ipynb`: Hello World with my name
- `Lesson_1.ipynb`: all exercises

**Tools:** Databricks Free Edition · PySpark · SQL · GitHub
