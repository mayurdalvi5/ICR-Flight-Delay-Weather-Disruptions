# ICR-Flight-Delay-Weather-Disruptions
Predicting Flight Delays Due to Weather Disruptions

# Collaborators
  - Ella Bronaugh
  - Reza Naiman
  - Tristan Levy-park
  - Mayur Dalvi

# Data Sources:
  - Flights Data :  https://www.transtats.bts.gov/DL_SelectFields.aspx?gnoyr_VQ=FGJ&QO_fu146_anzr=b0-gvzr

  - Weather Data : https://mesonet.agron.iastate.edu/request/download.phtml?network=NY_ASOS#


# Data Flow

  - **Flights_data_zip_merged_to_csv.ipynb**
      - Reads multiple zipped flight CSV files and merges them into a single file (**merged_2024.csv**).
      - As the Flights Data source we used did not have an API to fetch data and it was a static website, we were unable to use web scraping techniques.
      - Therefore, we had to manually download data for each month in zip files, and with this notebook, we were able to append data from all months into a single **merged_2024.csv** file.
      - The output of this notebook is **merged_2024.csv** [Download Here](https://mega.nz/file/DqpBETZY#SfYhBXu0RJV_5sapekPmgUr6WivNLpUfcD2Gt6UNBU0).
  
  - **Weather_Data_Collection.ipynb**
      - Fetches weather data via an API for a given date range and saves it for further analysis or merging with flight data.
      - For our selected Weather Data source, we had an API to fetch data, and it also provided a reference script to extract data (https://github.com/akrherz/iem/blob/main/scripts/asos/iem_scraper_example2.py#L1). We modified this script to suit our requirements and successfully retrieved the data.
      - The output of this notebook is **stations_20240101_20240201_filtered.csv** [Download Here](https://mega.nz/file/27ZmnC5a#5iM_0XQDnDQpKHoP5yv9nOznvI8T6SxnSauS3rhVEzE).

  - **Data_preprocessing_2024_Jan.ipynb**
      - This notebook has two parts:
          1. The first part creates a new column called `['departure_datetime']` using the `['FL_DATE']` and `['CRS_DEP_TIME']` columns. Please refer to the Flights Data Source for the definitions of these columns.
             - The output of this step is saved in **updated_merged_2024.csv** [Download Here](https://mega.nz/file/TjIFFQDQ#QAGhfsz-7LYMT07Y5NZtOdOgotEWZXayJIvP_RU8c_M).
          
          2. The second part reads **stations_20240101_20240201_filtered.csv** and **updated_merged_2024.csv** and merges both files to join the flight and weather data.
             - Before merging, the `datetime` columns in both files are rounded to the nearest hour. The `datetime` column in **stations_20240101_20240201_filtered.csv** is `['valid']`, and in **updated_merged_2024.csv**, it is `['departure_datetime']`. This results in two new columns: `['rounded_valid']` and `['rounded_departure']` for their respective files.
             - The two files are merged based on `['rounded_valid']`, `['rounded_departure']`, and `['station']`, `['ORIGIN']` (i.e., the name of the station and airport origin).
             - The final output after merging is **final_merged_2024.csv** [Download Here](https://mega.nz/file/imwAgJzQ#17ave0B5J0GUxS2N5Wd5rXzFEF8-we5MIvao6CSMDvI).

---

# Note

For now, we have only considered data from **New York State** and **January 2024**.

