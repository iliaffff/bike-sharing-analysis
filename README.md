# Bike Sharing Demand Analysis

Exploratory data analysis of bike-sharing demand using the UCI Bike Sharing Dataset.

## About the project

The goal of this project is to understand how bike rental demand changes depending on factors such as time of day, weather, season, and whether a day is a working day.

I used Python and pandas to explore the dataset, visualize different patterns, and apply some basic statistical analysis.

The main question I wanted to answer was:

> How does bike rental demand vary with time, weather, and working-day conditions?

## Dataset

The dataset comes from the UCI Machine Learning Repository:

https://archive.ics.uci.edu/dataset/275/bike+sharing+dataset

It contains hourly bike rental data from 2011 and 2012, with information about:

- Date and hour
- Season
- Working day / non-working day
- Weather conditions
- Temperature
- Humidity
- Wind speed
- Casual users
- Registered users
- Total rentals

The dataset contains 17,379 hourly observations.

## Tools

- Python
- Pandas
- NumPy
- Matplotlib
- SciPy
- Jupyter Notebook

## Analysis

The analysis was mainly focused on:

- Understanding the structure and quality of the data
- Exploring the distribution of bike rentals
- Analyzing rental demand by hour
- Comparing working days and non-working days
- Looking at seasonal patterns
- Studying the relationship between weather and rental demand
- Comparing casual and registered users
- Looking at correlations between numerical variables
- Performing a Welch's t-test
- Calculating a confidence interval
- Exploring effect size

## Some findings

### Time of day

Rental demand changes significantly throughout the day.

On working days, there are clear peaks around the morning and evening hours, especially around 7–8 AM and 5–6 PM.

On non-working days, rentals are more concentrated around the middle of the day, with the highest average demand around 1 PM.

### Season

Average rental demand was different across seasons.

| Season |  Average rentals  |
| Winter |      111.1        |
| Spring |      208.3        |
| Summer |      236.0        | 
| Fall   |      198.9        |

Summer had the highest average rental demand, while winter had the lowest.

### Weather

Rental demand was also lower under worse weather conditions.

The average number of rentals was approximately:

| Weather condition                    | Average rentals |
| Clear / partly cloudy                |      204.9      |
| Mist / cloudy                        |      175.2      |
| Light rain / snow                    |      111.6      |
| Heavy rain / other severe conditions |      74.3       |

### Casual vs registered users

Registered users made up most of the rentals in the dataset.

- Casual: ~18.8%
- Registered: ~81.2%

The two groups also showed different hourly patterns. Registered users had much stronger morning and evening peaks on working days, while casual users had higher demand during the middle of the day, especially on non-working days.

### Correlation

Some correlations with total rentals (`cnt`) were:

| Variable    |  Correlation with `cnt` |
| Temperature |   0.405 |
| Humidity    |  -0.323 |
| Windspeed   |   0.093 |

Temperature had the strongest linear correlation with rental demand among these weather variables.

These correlations describe associations in the data and should not be interpreted as causal relationships.

## Statistical analysis

I also compared the average hourly rental counts between working and non-working days.

The Welch's t-test gave:

- t-statistic: 4.095
- p-value: 0.0000425

The 95% confidence interval for the difference in mean rentals was:

`[6.15, 17.45]`

This suggests that the mean hourly rental count differs between working and non-working days in this dataset.

However, this is an observational dataset, and the comparison does not control for factors such as hour, season, or weather. Therefore, it should not be interpreted as evidence that working-day status itself causes the difference.

## Project structure

```text
bike-sharing-analysis/
│
├── data/
│   └── hour.csv
│
├── notebooks/
│   └── analysis.ipynb│   
│
├── README.md
└── requirements.txt