## Building an Automated Data Pipeline for Sales Data in Google Cloud
This repository contains the code and configuration files for the project, Building an Automated Data Pipeline for Sales Data in Google Cloud. This project demonstrates how to leverage multiple GCP services to develop an efficient, automated pipeline for processing sales data.

### Overview
This project implements a fully automated data pipeline for sales data management and reporting using Google Cloud Platform (GCP) services.
#### 1)Web Portal
Developed using Python Flask, this portal enables users to upload their sales data files easily.
#### 2)Storage
The uploaded files are securely stored in a Google Cloud Storage (GCS) bucket.

#### 3)Cloud Function
Automatically triggered upon file upload to the GCS bucket, this function processes the file, extracts the necessary data, and loads it directly into BigQuery.

#### 4)Data Processing
An automated process is implemented to extract, transform, and load (ETL) the data, ensuring it moves seamlessly from raw upload to a fully processed state ready for analysis.

#### 5)Data Visualization
Interactive dashboards and reports are created in Looker Studio, providing key metrics with options for filtering and in-depth analysis.

### Architecture:
![image](https://github.com/user-attachments/assets/44948bdb-3bc6-46c3-a9af-f7b17122730f)
### Explanation:
### 1. Data Submission

- **Users from Different Countries**: Individuals from various regions (India, UK, USA) interact with a web application to upload their sales data files. These files could be in formats such as CSV, Excel, or JSON, containing crucial sales information.
- **File Handling**: The process begins with the `upload_file` function in the Flask application. When a user uploads a file through the web interface, this file is sent to the Google Cloud Storage bucket for further processing.

### 2. Cloud Storage

- **File Upload to Cloud Storage**: Once the users submit their files through the web application, the files are automatically stored in Google Cloud Storage. This service acts as a scalable and secure storage solution where all sales data files are stored, organized by region, date, or other relevant categories. The Flask application code handles this by taking the uploaded file and using the Google Cloud Storage client to upload it to the specified bucket.

### 3. Cloud Functions

- **Triggering Cloud Functions**: A Google Cloud Function is configured to trigger automatically whenever a new file is uploaded to Cloud Storage. This serverless function is a critical component, as it handles the automation of data processing tasks without requiring server management.
- **Data Processing**: The Cloud Function code (`hello_gcs`) is triggered by the event of a file upload. It receives details about the file (such as its name and location) and calls the `load_bq` function to load the data into BigQuery. The `load_bq` function is responsible for performing operations such as data validation, transformation, or preprocessing, ensuring the data is in the correct format and structure before ingestion into BigQuery.

### 4. BigQuery

- **Data Ingestion into BigQuery**: After processing, the cleaned and structured sales data is loaded into BigQuery. BigQuery is Google Cloud’s fully-managed, serverless data warehouse that allows for fast SQL queries on large datasets. The Cloud Function's `load_bq` function loads the file data from Cloud Storage into the BigQuery table, using configurations like auto schema detection and skipping header rows if necessary.
- **Data Analysis**: Once the data is in BigQuery, it becomes available for complex analytical queries. This enables the extraction of insights, trends, and patterns from the sales data across different regions.

### 5. Looker Studio (Visualization and Reporting)

- **Connecting to Looker Studio**: Looker Studio, Google’s business intelligence tool, is connected to BigQuery to access the processed sales data.
- **Creating Visualizations**: Using Looker Studio, users can create interactive dashboards, reports, and visualizations that present the sales data in a user-friendly format. These visualizations help in monitoring performance, identifying trends, and making data-driven decisions.
- **Reporting**: The final reports are then made accessible to stakeholders, allowing them to gain insights into sales performance across different regions.
![image](https://github.com/user-attachments/assets/dc485856-65cb-4aa4-92ce-2f7c224f65c9)


## Summary

This architecture demonstrates an end-to-end automated data pipeline using Google Cloud services. It enables seamless data collection, processing, and visualization of sales data across different regions. The use of GCP services like Cloud Storage, Cloud Functions, BigQuery, and Looker Studio ensures that the pipeline is scalable, efficient, and capable of handling large volumes of data with minimal manual intervention.

The provided Flask application is used to handle file uploads and store them in Cloud Storage, while the Cloud Function code is triggered upon file uploads to process and load the data into BigQuery. This combination of tools and automation facilitates a streamlined workflow from data submission to insightful reporting.




