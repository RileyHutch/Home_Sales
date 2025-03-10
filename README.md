# Home Sales Data Analysis

## Overview
This project analyzes home sales data using Apache Spark and PySpark's SQL functionality. The analysis includes examining the relationship between home prices and various characteristics like number of bedrooms, bathrooms, square footage, and view ratings. The project also demonstrates the performance benefits of caching and partitioning in Spark.

## Technologies Used
- Apache Spark 3.5.5
- PySpark
- Python
- Google Colab

## Dataset
The analysis uses a dataset of home sales containing the following fields:
- id: Unique identifier for each home
- date: Date of sale
- date_built: Year the home was built
- price: Sale price
- bedrooms: Number of bedrooms
- bathrooms: Number of bathrooms
- sqft_living: Living area square footage
- sqft_lot: Lot size in square feet
- floors: Number of floors
- waterfront: Waterfront property (1) or not (0)
- view: A rating of the home's view

## Project Structure

### Setup and Configuration
- Import necessary packages and initialize Spark session
- Load home sales data from an AWS S3 bucket
- Create a temporary view of the DataFrame for SQL queries

### Analysis Tasks
1. Calculate the average price of four-bedroom houses sold per year
2. Determine the average price of homes by year built with 3 bedrooms and 3 bathrooms
3. Analyze average prices of homes by year built with 3 bedrooms, 3 bathrooms, 2 floors, and ≥2,000 sqft
4. Calculate the average price per view rating for homes priced ≥$350,000

### Performance Optimization
- Measure query runtime before optimization
- Cache the temporary table and compare runtime
- Partition the data by the "date_built" field and compare performance

## Key Findings
- The runtime comparison showed significant performance improvements:
  - Uncached runtime: ~0.77 seconds
  - Cached runtime: ~0.47 seconds (39% improvement)
  - Partitioned data runtime: ~0.62 seconds (19% improvement over uncached)