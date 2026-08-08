# 🌦️ Real-Time Weather Data ETL Pipeline Using OpenWeather API and Python

## 📌 Project Overview

This project demonstrates the development of a simple ETL (Extract, Transform, Load) pipeline using Python. The pipeline extracts real-time weather data from the OpenWeather API, transforms the raw JSON response into a clean and structured dataset using Pandas, and loads the processed data into a CSV file for future analysis.

The project was completed as part of the **AnalystLab Africa Batch B Internship – Week 7: Data Pipelines & Automation**.

---

## 🎯 Objectives

* Extract real-time weather data from the OpenWeather API.
* Transform the raw data into a structured and analysis-ready format.
* Load the processed data into a CSV file.
* Perform basic exploratory analysis on the collected weather data.

---

## Data Source

**Source:** OpenWeather API

The API provides real-time weather information for cities around the world, including:

* City Name
* Temperature (°C)
* Humidity (%)
* Weather Condition
* Wind Speed (m/s)
* Date and Time
---

🛠️ Tools & Technologies

* Tool             
* Python	          
* Pandas	         
* Requests	        
* OpenWeather     
* Jupyter Notebook	
* CSV	Data         
---

## ETL Process

### 1. Extract

* Connected to the OpenWeather API using an API key.
* Retrieved real-time weather data for three cities:

  * Lagos
  * Abuja
  * London

---

### 2. Transform

* Converted the JSON response into a Pandas DataFrame.
* Renamed columns for better readability.
* Converted the date and time column to the appropriate data type.
* Verified data quality by checking for missing values.
* Prepared a clean dataset for analysis.

---

### 3. Load

* Exported the cleaned dataset to a CSV file.
* Saved the processed data for future analysis and reporting.

---

## Dataset Fields

| Column            | Description                          |
| ----------------- | ------------------------------------ |
| City              | Name of the city                     |
| temperature       | Temperature in degrees Celsius       |
| humidity          | Relative humidity (%)                |
| weather_condition | Current weather description          |
| wind_speed        | Wind speed (m/s)                     |
| date_time         | Date and time the data was collected |

---

## Basic Analysis

The collected weather data was analyzed to compare weather conditions across the selected cities.

### Key Findings

* Weather data was successfully collected for Lagos, Abuja, and London.
* London recorded the highest temperature (**24.67°C**).
* Abuja had the highest humidity (**95%**).
* Weather Condistion differ between the cities.
   * Lagos - **Broken Clouds**
   * Abuja - **Overcast Clouds**
   * London - **Few Clouds**
* Lagos recorded the highest wind speed (**2.79 m/s**).
* The average temperature across the selected cities was **21.60°C**.
* The average humidity across the selected cities was **85.67%**.
* The Average wind speed across the selected cities was **1.85m/s**

---

## Project Structure

```text
Weather_ETL_Pipeline/
│
├── Data/
│   └── weather_data.csv
│
├── Notebook/
│   └── Weather_ETL_Pipeline.ipynb
│
└── README.md
```
---

🚀 How to Run the Project
* Clone the repository.
* Install the required libraries:
* pip install -r requirements.txt
* Open the Jupyter Notebook.
* Replace the API key with your own OpenWeather API key
* Run all notebook cells

---

## Conclusion

This project demonstrates how an ETL pipeline can automate the process of extracting real-time data from an API, transforming it into a clean and structured format, and loading it into a file for analysis. It also highlights the importance of data pipelines in preparing reliable datasets for business intelligence and data analytics.

---

## Author

**Danjuma Zainab**

Data Analytics Intern – AnalystLab Africa Batch B

Data Analyst Intern | Python | SQL | Excel | Power BI

 



