# CIS9650_Group16_Project_11
# Author:  Jiahuan Wu, Tenzin Sonam, Nuzhat Shahriyar, Humza Ali
# Final Project — NYC Green Taxi Trip Data Analysis
# Language: Python 3

# Project Overview
This project implements a full exploratory data analysis (EDA) pipeline for NYC Green Taxi trip data using Python, NumPy, Pandas, and data visualization tools.  
Given a Parquet file containing trip details (pickup time, dropoff time, distance, fare, tip, payment type, location IDs), the program:

- Loads the dataset directly from a public Google Cloud Storage bucket  
- Cleans and validates the data  
- Converts timestamp fields to proper datetime objects  
- Computes derived fields such as trip duration and tip percentage  
- Removes invalid or unrealistic records (e.g., negative fares, zero-distance trips, extreme durations)  
- Performs numerical and graphical analysis to answer business questions  
- Produces clear visualizations and interpretations

The project focuses on understanding relationships among trip distance, fare amount, tip behavior, payment preferences, and time-based demand patterns.

# Data File Requirements
The program requires access to the following public GCS file:
gs://msba-online-data/CIS9650/Project 11/green_tripdata_2025-06.parquet

# How to Run the Program
This project can be executed either on Google Colab or on a local machine.

Option 1 – Run on Google Colab (Recommended)
Open the notebook file in Google Colab:
CIS9650_final_project.ipynb
Run all cells in order.
The notebook will automatically load the dataset directly from Google Cloud Storage using the public bucket:
msba-online-data/CIS9650/Project11/green_tripdata_2025-06.parquet
No additional setup or installation is required.

Option 2 – Run Locally
Download the following files and place them in the same directory on your computer:
CIS9650_final_project.ipynb
green_tripdata_2025-06.parquet (optional, only if Google Cloud cannot be accessed)
Open the notebook using Jupyter Notebook, JupyterLab, or VS Code Notebook.
Run all cells in order.
The notebook will first attempt to load the dataset from Google Cloud Storage.
If the cloud dataset cannot be accessed, the notebook will automatically fall back to using the local Parquet file instead.

Requirements
Python 3.8+
Required packages (automatically installed in Colab):
pip install pandas pyarrow google-cloud-storage matplotlib numpy 

# Technical Analysis (NumPy, Pandas)
The analysis computes:
- Trip duration (minutes)
- Tip percentage
- Correlation between fare and distance
- Trend line estimation using NumPy (`np.polyfit`)
- Aggregations (`groupby`) for payment types and location frequencies
- Demand distribution across hours, days, and months

# Clean Output Formatting
All outputs are presented clearly with:
- Summary tables  
- Scatter plots with trend lines  
- Bar charts for categorical comparisons  
- Line charts for time-based trends  
- Inline interpretation after each visualization  

# Assumptions
- Dataset is correctly formatted with standard TLC taxi fields  
- Negative or impossible values indicate errors and must be removed  
- Trips longer than 180 minutes or over 50 miles are considered unrealistic  
- Tips over $50 are treated as outliers  
- Tip amounts are only reliably recorded for credit card transactions  

# Output
The program produces:
- Cleaned, validated DataFrame  
- Visual analyses answering the main business questions:  
  - Does fare increase linearly with distance?  
  - What factors influence tipping?  
  - What locations are most popular?  
  - When is demand highest?  
- A final conclusion summarizing insights  


