# Bay Area Bike Share Analysis

An exploratory data analysis of Bay Area Bike Share trip data, completed as the introductory project for the Udacity Data Analyst Nanodegree. The project walks through the data wrangling and exploratory analysis stages of the data analysis process: sampling and cleaning raw trip records, computing summary statistics, and building histograms to compare ridership patterns across cities.

**View the rendered analysis:** [Bay_Area_Bike_Share_Analysis.html](https://rfhickey.github.io/BayAreaBikeShare/Bay_Area_Bike_Share_Analysis.html)

This repository contains only the rendered HTML export of the analysis notebook; the source Jupyter (IPython) notebook is not included in the repo.

## Data

The analysis uses trip, station, and weather data published by [Bay Area Bike Share](http://www.bayareabikeshare.com/open-data) (the system later became Ford GoBike, then Bay Wheels; the original open data page may no longer be live). The dataset covers two periods:

- Year 1: August 2013 through August 2014
- Year 2: September 2014 through August 2015

Trips span five cities: San Francisco, Redwood City, Palo Alto, Mountain View, and San Jose. Each trip record includes duration, start and end stations, and rider subscription type (Subscriber or Customer).

## Method

The notebook first works with a one-month sample (August 29 to September 30, 2013) to build and verify a data wrangling routine before applying it to the full two-year dataset. Wrangling steps include converting trip duration from seconds to minutes, splitting start timestamps into year, month, hour, and weekday fields, and mapping station terminals to their home city. Two helper modules provided with the project, `babs_datacheck.py` and `babs_visualizations.py`, supply a data-check function used to verify the wrangling output and `usage_stats()` / `usage_plot()` functions used to summarize trip counts, duration statistics, and duration histograms, optionally filtered by city or other trip attributes.

## Key findings

- Across the full two-year dataset, San Francisco accounted for the large majority of trips: 603,708 trips (90.11% of all trips), compared to 37,878 in San Jose (5.65%) and 18,167 in Mountain View (2.71%).
- Average trip duration differed by city even though median durations were similar or shorter: San Francisco averaged 17.12 minutes (median 8.75), San Jose averaged 23.01 minutes (median 7.67), and Mountain View averaged 29.89 minutes (median 4.95). Because San Jose and Mountain View have far fewer short rides than San Francisco, their averages are pulled upward without necessarily reflecting more long rides.
- In the one-month sample used to develop the wrangling code (27,345 trips), the most common trip length was 5 to 10 minutes (roughly 9,000 trips), with an overall average duration of 27.60 minutes and a median of 10.72 minutes.

## Repository structure

- `Bay_Area_Bike_Share_Analysis.html`: rendered HTML export of the analysis notebook, including code, output tables, histograms, and written answers to the project's guided questions.
- `README.md`: this file.
- `LICENSE`: MIT license.

## How to run

The source notebook is not included in this repository, so there is nothing to execute directly; open `Bay_Area_Bike_Share_Analysis.html` in a browser, or view it via the GitHub Pages link above, to see the full analysis with its code and output.

For reference, the original notebook was written in Python 2 (based on the syntax highlighting in the export) using `csv`, `datetime`, `numpy`, and `pandas`, plus the project-provided `babs_datacheck` and `babs_visualizations` helper modules. Library versions are historical to 2018 and are not pinned here.

## License

Released under the MIT License. See [LICENSE](LICENSE) for details.
