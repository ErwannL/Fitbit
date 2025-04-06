# Fitbit Data Analysis Report

## Executive Summary

As part of our student project at Hanze University, we analyzed a dataset of Fitbit user activity to develop a predictive model for daily step goal achievement. Working with provided CSV files containing historical Fitbit data, we created a model that achieved 97% accuracy in predicting whether users would reach their daily step goals.

## Introduction

For this project, we were provided with Fitbit activity data collected during the "Het Nieuwe Gezonde Werken" (HNGW) initiative at Hanze University. Our assignment was to analyze this historical data and develop a model that could predict step goal achievement.

Our project objectives were to:
1. Analyze the provided Fitbit data to understand user activity patterns
2. Develop a prediction model using the available data
3. Identify which factors best indicate whether someone will reach their step goal

## Methodology and Justification

As students approaching this data analysis project, we made several key decisions about how to work with the provided dataset.

The data we received consisted of CSV files in the Data Coaching Fitbit directory, containing activity records for several users. After examining the available data, we decided to focus on workday activity (Monday-Friday) up to 18:00. We chose this scope because:
- It provided a consistent pattern of activity to analyze
- Most users showed similar workday routines
- The 18:00 cutoff gave us enough daily data to make predictions

From the available variables in our CSV files, we focused on four main metrics:
- Steps
- Distance
- METs (Metabolic Equivalent of Task)
- Calories
These were the most complete and reliable measurements in our dataset, with very few missing values.

When processing the data, we found that only 0.11% of step records were missing. Given the small percentage, we simply removed these records rather than trying to estimate missing values. As students learning data analysis, we felt this was a more straightforward approach than using complex imputation methods.

To get more insight from our data, we created additional calculations:
- Daily progress (how many steps taken so far)
- Required pace (steps needed per hour to reach goal)
- Hourly activity rates

For our prediction model, we chose the Random Forest algorithm because:
- It was covered in our machine learning courses
- It can handle the different types of data we had
- It's good at finding patterns in activity data
- It tells us which factors are most important

We split our available users into two groups:
Training data: Users 1121, 1123, 1122, and 1125
Testing data: Users 1119, 1120, and 1124

We noticed that about 65% of the time users didn't reach their step goals, while 35% of the time they did. To handle this imbalance, we used a technique called SMOTE that we learned about in our data science courses.

## Results and Impact

Our model performed well on the test data, achieving 97% accuracy. This was much better than simply guessing that users would never reach their goals (which would be right 65% of the time).

Looking at what helped predict step goal achievement, we found three main factors:
- Current step count (31.12% importance)
- Steps still needed (28.68% importance)
- Average steps per hour (22.45% importance)

When analyzing our model's mistakes, we found some interesting patterns:
- It was more likely to wrongly predict success (2.3% false positives) in late morning during spring/summer
- It was less likely to predict success correctly (0.8% false negatives) in early morning during winter

## Recommendations

Based on our analysis of the historical data, we suggest:
1. Tracking progress throughout the day
2. Paying special attention to morning activity levels
3. Considering seasonal differences in activity patterns

For future student projects, we recommend:
- Collecting weather data to see its impact
- Recording different types of activities
- Tracking when users receive encouragement
- Creating personalized goals
- Adjusting goals based on past performance
- Looking at longer-term predictions

## References

1. HNGW Project Documentation
2. Course Materials on Machine Learning
3. Data Science Best Practices

## Appendix

Our complete analysis can be found in these Python notebooks:
- final.ipynb: Main analysis
- model.ipynb: Prediction model development
- code.ipynb: Data processing steps
- average.ipynb: Statistical calculations