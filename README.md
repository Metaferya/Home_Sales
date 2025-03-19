# Home_Sales
## Overview

This project utilizes Apache Spark and PySpark SQL to analyze a dataset of home sales. The goal is to extract insights such as average home prices based on different conditions, optimize query performance using caching and partitioning, and compare execution times across different storage formats.

## Technologies Used

- **Python**
- **Apache Spark (PySpark)**
- **AWS S3 (Dataset Source)**
- **Parquet File Format**

## Dataset

The dataset used in this project is `home_sales_revised.csv`, sourced from an AWS S3 bucket. It contains data on home sales, including attributes like:

- Number of bedrooms and bathrooms
- Square footage
- Date built
- Price
- View rating

## Key Tasks and Analysis

1. **Load the Dataset into a Spark DataFrame**

   - Read `home_sales_revised.csv` into a Spark DataFrame.
   - Create a temporary table `home_sales` for querying.

2. **Data Analysis Using SparkSQL**

   - Calculate the average price of four-bedroom houses sold per year.
   - Determine the average price of homes with three bedrooms and three bathrooms per year built.
   - Find the average price of homes with three bedrooms, three bathrooms, two floors, and a size ≥ 2,000 sqft per year built.
   - Calculate the average price of homes per `view` rating with an average price ≥ \$350,000.

3. **Performance Optimization**

   - **Caching:** Cache the `home_sales` table and re-run queries to compare execution times.
   - **Partitioning:** Partition data by `date_built` and save it in Parquet format.
   - **Query on Parquet Data:** Run queries on partitioned Parquet data and compare performance with uncached and cached queries.

4. **Verification and Cleanup**

   - Validate caching and uncaching operations.
   - Measure and compare query run times.

## Results

- SparkSQL enabled efficient data querying and aggregation.
- Caching significantly improved query performance by reducing execution time.
- Partitioning and using Parquet format further optimized data retrieval speed.

## How to Run the Project

1. Ensure Apache Spark and PySpark are installed.
2. Load the dataset from AWS S3.
3. Execute the Jupyter Notebook or Python script to run queries and analyze performance.
4. Compare query execution times before and after caching and partitioning.

## File Structure

```
📂 Home_Sales_Project
 ├── Home_Sales.ipynb        # Jupyter Notebook with full implementation
 ├── home_sales_revised.csv  # Dataset (from AWS S3)
 ├── home_sales_partitioned/ # Parquet-formatted dataset (output)
 ├── README.md               # Project documentation
```

## Author

- Fitsum G. Metaferya
- Data Science Enthusiast

## License

This project is for educational purposes only

---

### Notes:

- Ensure you have proper Spark and PySpark setup before running the notebook.
- The dataset is large, so performance optimizations such as caching and partitioning are crucial.

Happy Analyzing! 🚀

