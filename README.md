# 🌦️ # Real-Time Weather Data ETL Pipeline

An ETL (Extract, Transform, Load) pipeline built with Python that collects live weather data for **Lagos, Abuja and London** from the OpenWeather API, cleans it with Pandas, saves it to CSV, and analyses the differences between the cities.

> Week 7 project, AnalystLab Africa Data Analytics Internship Program

---

## Business Problem

Weather-dependent decisions in logistics, agriculture, events and retail need fast, reliable data. Raw API responses are nested JSON and are not ready for analysis. This project automates the path from raw API response to a clean, analysis-ready dataset.

## Objective

Collect real-time weather data for multiple cities, clean and structure it, store it for analysis, and generate insights from the processed dataset.

## Tools and Technologies

| Tool | Purpose |
|------|---------|
| Python | Core programming language |
| Requests | Calling the OpenWeather API |
| Pandas | Data cleaning and analysis |
| Matplotlib | Data visualisation |
| Jupyter Notebook | Development environment |
| CSV | Storage format |
| GitHub | Version control and sharing |

## How the Pipeline Works

1. **Extract:** Loop through the list of cities and request current weather (metric units) from the OpenWeather API.
2. **Transform:**
   - Convert the JSON responses into a Pandas DataFrame
   - Check structure and data types with `df.info()`
   - Check for missing values with `df.isnull().sum()` (0 found)
   - Rename columns to clean snake_case names
   - Convert `date_time` to a true datetime type
3. **Load:** Save the cleaned dataset to `weather_data.csv`.
4. **Analyse and visualise:** Compare temperature, humidity, wind speed and conditions across cities, then plot bar charts.

## Dataset

Snapshot taken on **8 August 2026, 07:43**.

| City | Temperature (°C) | Humidity (%) | Wind Speed (m/s) | Condition |
|------|------------------|--------------|------------------|-----------|
| Lagos | 24.67 | 89 | 2.79 | Broken Clouds |
| Abuja | 22.57 | 95 | 1.87 | Overcast Clouds |
| London | 17.57 | 73 | 0.89 | Few Clouds |
| **Average** | **21.60** | **85.67** | **1.85** | - |

**Fields:** `City`, `temperature`, `humidity`, `weather_condition`, `wind_speed`, `date_time`

## Key Insights

- **Lagos** was the warmest and windiest city (24.67°C, 2.79 m/s). It is a coastal city, so warm ocean air and sea-driven air movement likely explain this.
- **Abuja** was the most humid (95%), which fits the peak of the August rainy season.
- **London** was the coolest and calmest (17.57°C, 0.89 m/s), about 6°C below the Nigerian cities' average of 23.62°C, consistent with its temperate climate and an early-morning reading.
- **Cloud cover tracked humidity:** overcast Abuja (95%), broken-cloud Lagos (89%) and few-cloud London (73%).
- The overall averages (21.60°C, 85.67% humidity, 1.85 m/s) blend very different climates, so city-level comparisons are more meaningful than the combined average.

> The explanations above are likely climate-based reasons, not proven causes. With one reading per city, they are hypotheses to test with more data.

## Recommendations

1. **Schedule the pipeline** (Task Scheduler, cron or GitHub Actions) and append each run to the dataset, so snapshots become trends.
2. **Add error handling and validation:** check response status codes, handle failed cities, and validate value ranges (for example, humidity between 0 and 100).
3. **Use the API's observation time** (the `dt` field in UTC) instead of the computer's clock.
4. **Expand the scope:** add more cities and fields such as feels-like temperature, pressure and rainfall.
5. **Build a dashboard** in Power BI or on top of a SQL table to track trends over time.
6. **Apply the insights:** use humidity and rain signals for delivery and event planning in rainy-season cities.

## Limitations

- One snapshot per city (3 records), so no trends can be drawn yet.
- Readings reflect a single early-morning moment, not daily or seasonal averages.
- The CSV is overwritten on each run, so no history is kept.

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Xee-xainab/OPen .git
cd <your-repo-name>
```

### 2. Install the requirements

```bash
pip install requests pandas matplotlib jupyter
```

### 3. Add your OpenWeather API key

Create a free account at [openweathermap.org](https://openweathermap.org/api) and generate an API key. **Never write your key directly in the notebook.** Store it as an environment variable:

```bash
# macOS / Linux
export OPENWEATHER_API_KEY="your_key_here"

# Windows (PowerShell)
$env:OPENWEATHER_API_KEY="your_key_here"
```

Then load it in the notebook:

```python
import os
API_KEY = os.getenv("OPENWEATHER_API_KEY")
```

### 4. Run the notebook

```bash
jupyter notebook Weather_Data_ETL_Pipeline.ipynb
```

Results will differ from the table above, because the notebook pulls live weather each time it runs.

## Repository Structure

```
.
├── Weather_Data_ETL_Pipeline.ipynb    # ETL pipeline, analysis and visualisations
├── weather_data.csv                   # Cleaned dataset
├── Weather_ETL_Insights_Report.pdf    # Full insights report
└── README.md
```

## Author

**Zainab Danjuma**
Data Analytics Intern, AnalystLab Africa



