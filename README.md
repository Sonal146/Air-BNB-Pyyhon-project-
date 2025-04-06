# Airbnb Data Analysis Project


## Overview
 A deep dive into Airbnb data using Python. I cleaned, explored, visualized, and even built predictive models to help hosts and guests make smarter decisions. With top-notch libraries like Pandas, NumPy, Matplotlib, and Seaborn, I turned messy data into clear, actionable insights—no cap.

## Table of Contents
Project Motivation

Technologies Used

Project Workflow

Key Findings & Insights

How to Run the Project

Future Enhancements

License

## Project Motivation
Airbnb’s platform is huge, and understanding what drives listing prices and guest preferences is crucial. In this project, I set out to:

Clean and prepare data: Say goodbye to dirty data—this project handles missing values, outliers, and type inconsistencies.

Explore data trends: Analyze trends in room types, neighborhood distribution, and price ranges.

Visualize insights: Create killer visuals that make the data speak volumes.

Build predictive models: Develop models to estimate listing prices based on key features.

## Answer key questions:

### What’s the distribution of prices?
plt.figure(figsize=(10, 6))
sns.histplot(df['price'], bins=50, kde=True, color='blue')

plt.title("Distribution Of Price")

plt.xlabel("price $")
plt.ylabel("Frequency")

plt.show()



### How do room types affect pricing?

plt.figure(figsize=(8, 5))
sns.countplot(x='room type', data=df, color='hotpink')

plt.title('Room Type Distribution')
plt.xlabel('Room Type')

plt.ylabel('Count')
plt.show()


### Which neighborhoods show distinct trends?
plt.figure(figsize=(12, 8))
sns.countplot(y='neighbourhood group', data=df, color='lightgreen', order=df['neighbourhood group'].value_counts().index)
plt.title('Number of Listings by Neighborhood Group')
plt.xlabel('Count')
plt.ylabel('Neighborhood Group')
plt.show()


### How does price vary by room type?

import matplotlib.pyplot as plt
import seaborn as sns

plt.figure(figsize=(10, 6))
sns.boxplot(x='room type', y='price', hue='room type', data=df, palette='Set1')
plt.title('Price vs. Room Type')
plt.xlabel('Room Type')
plt.ylabel('Price ($)')
plt.legend(title='Room Type')
plt.show()


#### Review Variations Over Time 

#### import pandas as pd
import matplotlib.pyplot as plt


#### Convert ' last review ' column to datetime objects
df['last review'] = pd.to_datetime(df['last review'])

#### Group by month and count the number of reviews
reviews_over_time = df.groupby(df['last review'].dt.to_period('M')).size()

#### Create the plot
plt.figure(figsize=(12, 6))
reviews_over_time.plot(kind='line', color='hotpink')
plt.title('Number of Reviews Over Time')
plt.xlabel('Date')
plt.ylabel('Number of Reviews')
plt.show()


## Technologies Used

### Python: The powerhouse behind the project.

### Pandas & NumPy: For robust data manipulation and cleaning.

### Matplotlib & Seaborn: To create stunning, easy-to-digest visualizations.

##3 Jupyter Notebook: For an interactive, step-by-step analysis process.

## Project Workflow
### Data Collection & Cleaning

### Gathered raw Airbnb data and cleaned it by handling missing values and outliers.

### Standardized data formats to make analysis a breeze.

### Exploratory Data Analysis (EDA)

### Explored key features like price, room type, and neighborhood distribution.

### Used descriptive statistics to get a feel for the dataset.

### Visualization

Crafted clear, eye-catching charts (histograms, bar plots, heatmaps) to showcase trends.

Visualized the distribution of prices and compared room types and neighborhoods.

Feature Engineering & Model Building

### Developed new features that boost model performance.

### Built predictive models for price estimation to validate the insights.

Insights & Conclusion

Extracted actionable insights: which features drive higher prices and how guests’ preferences vary across neighborhoods.

Provided recommendations for hosts and guests based on the analysis.

## Key Findings & Insights
Price Distribution: Most listings fall within a mid-range price bracket, but outliers (those crazy high-priced properties) definitely skew the averages—something to keep in mind!

Room Type Analysis: Entire homes/apartments are the most common and fetch the highest prices, while private rooms are budget-friendly alternatives.

Neighborhood Trends: Certain neighborhoods consistently offer higher price points, hinting at location-based desirability.

Price vs. Room Type: There’s a clear relationship between room type and pricing, offering a roadmap for hosts looking to maximize revenue.

## How to Run the Project
Clone the Repository:



## Run the Notebook:
Launch Jupyter Notebook and open the project notebook:

bash
Copy
Edit
jupyter notebook
Then, run the cells to see the analysis in action.
