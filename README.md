# Uefa Champions League 2024/25 Analysis

Project that analyzes the Uefa Champions League 2024/25 League Phase using Python and Power BI. It combines data extraction, cleaning, and transformation with interactive visualizations to explore team and player performances throughout the competition.

[Click here to access the Power BI report](https://app.powerbi.com/view?r=eyJrIjoiNTQ0OGQyZDItM2IxYS00YWYyLWJhZWUtOTZlZTJlNzAzY2I2IiwidCI6ImFmNmE0MmI1LWJkMGUtNDUwNS1iMDdmLWY5MTdiMGNlMmYzZCJ9)

## Objectives

- Analyze individual player statistics and team performances during the 2024/25 Champions League League Phase.
- Extract, clean, and consolidate match and player data from FBref.
- Calculate Field Tilt to measure each team's share of touches in the attacking third.
- Build a structured dataset to support interactive visualizations and performance analysis in Power BI.

## Technologies Used

- **Python:** data extraction, cleaning, transformation, and metric calculation.
- **Pandas:** HTML table extraction, data manipulation, merging, and CSV processing.
- **Regular Expressions (re):** text cleaning and standardization.
- **Time:** request delays during data extraction.
- **Google Colab:** notebook execution and Google Drive integration.
- **Power BI:** data modeling, interactive reports, and visualizations.

## Data Processing and Methodology

The project is organized into three main Python notebooks:

### 1. Extracting Player Statistics

The `extracting-stats.ipynb` notebook collects player statistics from individual match pages on FBref. It extracts tables covering different aspects of player performance, merges the relevant data, removes aggregate player rows, standardizes column names, and adds match identifiers, matchday information, and team names.

The resulting dataset consolidates player performances across the competition.

### 2. Calculating Field Tilt

The `field-tilt.ipynb` notebook uses the consolidated player statistics to calculate Field Tilt for each team in each match.

The calculation is based on the team's share of total touches in the attacking third:

**Field Tilt = Team attacking-third touches / Total attacking-third touches by both teams**

The notebook also calculates a cumulative version of the metric across matches and converts the results into percentages, rounded to two decimal places.

### 3. Extracting Match Fixtures

The `extracting-fixtures.ipynb` notebook retrieves match information from FBref's Champions League fixtures table. It cleans and standardizes team names, removes incomplete or duplicated header rows, separates home and away scores, and renames expected-goals columns for clarity.

The fixture data provides match-level context that complements the player statistics and Field Tilt calculations.

## Data Sources

- [FBref – Uefa Champions League](https://fbref.com/en/comps/8/Champions-League-Stats): match reports, player statistics, and fixtures.
- [Complete datasets](complete-data/): processed CSV files used in the project.

## Project Structure

- `python-notebooks/extracting-stats.ipynb`: extracts, cleans, and consolidates player statistics.
- `python-notebooks/field-tilt.ipynb`: calculates match-level and cumulative Field Tilt.
- `python-notebooks/extracting-fixtures.ipynb`: extracts and cleans match fixtures and results.
- `complete-data/statsucl2425.csv`: consolidated player statistics.
- `complete-data/fieldtiltucl2425.csv`: Field Tilt data.
- `complete-data/fixturesucl2425.csv`: match fixtures and results.
- `.pbip-files/`: Power BI report and semantic model project files.
- `pbipucl2425.pbip`: Power BI Project entry file.

