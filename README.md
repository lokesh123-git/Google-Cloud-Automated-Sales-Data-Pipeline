## Building an Automated Data Pipeline for Sales Data in Google Cloud
This repository contains the code and configuration files for the project, Building an Automated Data Pipeline for Sales Data in Google Cloud. This project demonstrates how to leverage multiple GCP services to develop an efficient, automated pipeline for processing sales data.
## Overview
### Web Portal: 
Developed using Python Flask, this portal enables users to upload their sales data files easily.
### Storage: 
The uploaded files are securely stored in a Google Cloud Storage (GCS) bucket.
### Cloud Function: 
Automatically triggered upon file upload to the GCS bucket, this function processes the file, extracts the necessary data, and loads it directly into BigQuery.
### Data Processing: 
An automated process is implemented to extract, transform, and load (ETL) the data, ensuring it moves seamlessly from raw upload to a fully processed state ready for analysis.
### Data Visualization: 
Interactive dashboards and reports are created in Looker Studio, providing key metrics with options for filtering and in-depth analysis.





