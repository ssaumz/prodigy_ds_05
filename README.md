# README: Task-05 - Data Science Internship at Prodigy InfoTech

## Project Overview

Excited to announce the successful completion of Task-05 during my data science internship at Prodigy InfoTech 🚀. This project involved analyzing traffic accident data to identify patterns related to road conditions, weather, and time of day, and visualizing accident hotspots and contributing factors using Python in Jupyter Notebook.

## Table of Contents

1. [Project Description](#project-description)
2. [Technologies Used](#technologies-used)
3. [Setup and Installation](#setup-and-installation)
4. [Usage](#usage)
5. [Project Structure](#project)
6. [Contributors](#contributors)

## Project Description

Task-05 focused on the analysis of traffic accident data to uncover patterns and trends related to road conditions, weather, and time of day. The project included data preprocessing, analysis, and visualization of accident hotspots and contributing factors.

### Objectives

- Preprocess the traffic accident dataset.
- Analyze the dataset to identify patterns and trends related to road conditions, weather, and time of day.
- Visualize accident hotspots and contributing factors using various plotting techniques.
- Interpret the results to provide insights into traffic accidents and their causes.

## Technologies Used

- **Python**: Programming language used for data manipulation, analysis, and visualization.
- **Jupyter Notebook**: Interactive computing environment for writing and running code.
- **Pandas**: Data manipulation library.
- **NumPy**: Numerical computing library.
- **Matplotlib**: Visualization library for creating static plots.
- **Seaborn**: Statistical data visualization library based on Matplotlib.
- **Folium**: Library for visualizing geospatial data.

## Setup and Installation

### Prerequisites

Ensure you have the following software installed:

- Python (version 3.6 or higher)
- Jupyter Notebook


### Running the Notebook

1. Launch Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

2. Open the notebook file `Task-05-Traffic-Accident-Analysis.ipynb` and run the cells sequentially.

## Usage

### Example Usage

The notebook provides a step-by-step guide on how to:

1. Load and preprocess the traffic accident dataset.
2. Analyze patterns related to road conditions, weather, and time of day.
3. Visualize accident hotspots using geospatial data.
4. Identify contributing factors to traffic accidents.

#### Data Collection and Preprocessing

```python
import pandas as pd

# Load dataset
data = pd.read_csv('data/traffic_accidents.csv')

# Display the first few rows of the dataset
data.head()

# Preprocess data (e.g., handle missing values, convert data types)
data.dropna(subset=['latitude', 'longitude'], inplace=True)
data['date_time'] = pd.to_datetime(data['date_time'])
```

#### Analyzing Patterns

```python
# Extract hour, day of week, and month from date_time
data['hour'] = data['date_time'].dt.hour
data['day_of_week'] = data['date_time'].dt.day_name()
data['month'] = data['date_time'].dt.month_name()

# Analyze accidents by time of day
accidents_by_hour = data['hour'].value_counts().sort_index()

# Analyze accidents by day of week
accidents_by_day = data['day_of_week'].value_counts()

# Analyze accidents by month
accidents_by_month = data['month'].value_counts()
```

#### Visualizing Patterns

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Plot accidents by time of day
plt.figure(figsize=(10, 6))
sns.barplot(x=accidents_by_hour.index, y=accidents_by_hour.values, palette='viridis')
plt.title('Accidents by Hour of Day')
plt.xlabel('Hour of Day')
plt.ylabel('Number of Accidents')
plt.show()

# Plot accidents by day of week
plt.figure(figsize=(10, 6))
sns.barplot(x=accidents_by_day.index, y=accidents_by_day.values, palette='viridis')
plt.title('Accidents by Day of Week')
plt.xlabel('Day of Week')
plt.ylabel('Number of Accidents')
plt.show()

# Plot accidents by month
plt.figure(figsize=(10, 6))
sns.barplot(x=accidents_by_month.index, y=accidents_by_month.values, palette='viridis')
plt.title('Accidents by Month')
plt.xlabel('Month')
plt.ylabel('Number of Accidents')
plt.show()
```

## Project Structure

```
prodigy-infotech-task-05/
├── data/
│   └── road_accidents.csv  # Sample dataset
├── images/
│   └── prodigy_ds_05.png  # Example of generated plot for accidents by hour
├── prodigy_ds_05.ipynb  # Jupyter Notebook file
└── README.md  

## Contributors

-**Saumya Poojari** - [saumya.poojarii7@gmail.com]

-LinkedIn - https://www.linkedin.com/in/ssaumz/

Feel free to reach out with any questions or feedback!

---

Thank you for your interest in this project. Happy coding! 🚀
