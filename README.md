# Home Sales Analysis

## Project Overview

This project utilizes SparkSQL to analyze home sales data from an AWS S3 bucket. The aim is to determine key metrics about the home sales and demonstrate various functionalities of SparkSQL such as creating temporary views, partitioning data, caching and uncaching temporary tables, and verifying table states. 

## Dataset

The dataset used in this project is a CSV file containing home sales data, which includes information about the sale price, number of bedrooms, bathrooms, the date the home was built, and other relevant details.

## Files

- `Home_Sales.ipynb`: The Jupyter notebook containing the code for the analysis.
- `home_sales_revised.csv`: The CSV file with the home sales data (available via a URL in the code).

## Instructions

1. Clone the repository to your local machine.
2. Ensure that you have the necessary dependencies installed (PySpark, Pandas).
3. Open the `Home_Sales.ipynb` notebook.
4. Follow the instructions in the notebook to run the analysis.

## Analysis and Results

### 1. Average Price for Four-Bedroom Houses Sold per Year

The first query calculates the average price for four-bedroom houses sold each year. The results are rounded to two decimal places.

#### Results:
| Year | AvgPrice |
|------|----------|
| 2019 | 300623.7 |
| 2020 | 298353.78 |
| 2021 | 301819.44 |
| 2022 | 296363.88 |

### 2. Average Price of Homes with Three Bedrooms and Three Bathrooms per Year Built

The second query calculates the average price of homes with three bedrooms and three bathrooms for each year the home was built. The results are rounded to two decimal places.

#### Results:
| YearBuilt | AvgPrice |
|-----------|----------|
| 2010      | 292859.62|
| 2011      | 291117.47|
| 2012      | 293683.19|
| 2013      | 295662.27|
| 2014      | 298852.27|
| 2015      | 288770.3 |
| 2016      | 295555.07|
| 2017      | 292676.79|

### 3. Average Price of Homes with Specific Features

The third query calculates the average price of homes with three bedrooms, three bathrooms, two floors, and a living area greater than or equal to 2,000 square feet for each year the home was built. The results are rounded to two decimal places.

#### Results:
| YearBuilt | AvgPrice |
|-----------|----------|
| 2010      | 285010.22|
| 2011      | 276553.81|
| 2012      | 307539.97|
| 2013      | 303676.79|
| 2014      | 298264.72|
| 2015      | 297699.57|
| 2016      | 293965.1 |
| 2017      | 288317.58|

### 4. Average Price of Homes by "View" Rating with Minimum Price

The fourth query calculates the average price of homes by "view" rating, considering only those homes with an average price greater than or equal to $350,000. The results are rounded to two decimal places, and the runtime for the query is measured.

#### Results:
| View | AvgPrice   |
|------|------------|
| 100  | 1026669.5  |
| 99   | 1061210.42 |
| 98   | 1053739.33 |
| 97   | 1129040.15 |
| 96   | 1017815.92 |
| 95   | 1054325.6  |
| 94   | 1033536.2  |
| 93   | 1026006.06 |
| 92   | 974002.55  |
| 91   | 1137372.73 |
| 90   | 1062654.16 |
| 89   | 1107839.15 |
| 88   | 1031719.35 |
| 87   | 1072285.2  |
| 86   | 1070444.25 |
| 85   | 1056336.74 |
| 84   | 1117233.13 |
| 83   | 1033965.93 |
| 82   | 1063498.0  |
| 81   | 1053472.79 |

#### Runtime:
- Without cache: 0.316 seconds
- With cache: 0.143 seconds

### 5. Partitioning Data and Comparing Runtime

The data was partitioned by the "date_built" field and stored in Parquet format. The query from step 4 was then run on the partitioned data, and the runtime was measured.

#### Runtime with partitioned data: 0.280 seconds

### Conclusion

The project demonstrates how to perform data analysis using SparkSQL, including creating temporary views, caching, and partitioning data. The results show the average prices of homes based on different criteria and highlight the performance improvements achieved by caching and partitioning the data.


