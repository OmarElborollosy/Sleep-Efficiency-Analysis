

# Sleep Efficiency Analysis Project

## Overview

The Sleep Efficiency Analysis project delves into the intricate factors affecting sleep quality. By leveraging a comprehensive dataset containing sleep metrics and demographic information, we aim to understand the impact of various lifestyle choices on sleep efficiency.

## Dataset

The dataset comprises essential sleep-related features and demographic details:

- **Age**: Age of the individual
- **Gender**: Gender of the individual
- **Bedtime**: Time the individual went to bed
- **Wakeup_time**: Time the individual woke up
- **Sleep_duration**: Duration of sleep
- **Sleep_efficiency**: Efficiency of sleep
- **REM_sleep_percentage**: Percentage of REM sleep
- **Deep_sleep_percentage**: Percentage of deep sleep
- **Light_sleep_percentage**: Percentage of light sleep
- **Awakenings**: Number of times the individual woke up during sleep
- **Caffeine_consumption**: Amount of caffeine consumed
- **Alcohol_consumption**: Amount of alcohol consumed
- **Smoking_status**: Smoking status (Yes/No)
- **Exercise_frequency**: Frequency of exercise (0-5 times a week)
- **Date**: Date of the record
- **Hour**: Hour of the record

## Data Preprocessing

- **Handling Missing Values**:
    - Filled missing values in columns (Awakenings, Caffeine_consumption, Alcohol_consumption, and Exercise_frequency) with the mode of each respective column.

```python
awakenings_mode = df['Awakenings'].mode()[0]
df['Awakenings'].fillna(awakenings_mode, inplace=True)
# Repeat for other columns
```

- **Encoding Categorical Variables**:
    - Encoded the Smoking_status column to numeric values (0 for 'No' and 1 for 'Yes') for compatibility with machine learning models.

## Exploratory Data Analysis (EDA)

- Visualized relationships between sleep metrics and lifestyle factors (smoking, alcohol consumption, exercise frequency).

## Findings

1. **Smoking**:
    - Smokers exhibit lower sleep efficiency and reduced deep sleep duration.
2. **Alcohol Consumption**:
    - Higher alcohol consumption correlates with lower sleep efficiency, decreased deep sleep, and increased light sleep duration.
3. **Exercise Frequency**:
    - Regular exercise (4-5 times a week) positively impacts sleep efficiency, promoting more deep sleep and less light sleep.

## Machine Learning Model

- Utilized a **Gradient Boosting Regressor** to predict sleep efficiency based on key features:
    - Deep_sleep_percentage
    - Light_sleep_percentage
    - Awakenings
    - Alcohol_consumption
    - Smoking_status
    - Exercise_frequency

## Model Performance

- **Mean Squared Error (MSE)**: 0.0026
- **R² Score**: 0.8571 (explaining approximately 85.71% of variance in sleep efficiency)

## Feature Importance

- **Light_sleep_percentage**: 0.4500
- **Deep_sleep_percentage**: 0.3292
- **Awakenings**: 0.1393
- **Smoking_status**: 0.0340
- **Alcohol_consumption**: 0.0243
- **Exercise_frequency**: 0.0229

## Interpretation

- The model provides valuable insights, with **Light_sleep_percentage** and **Deep_sleep_percentage** being the most influential features.

## Conclusion

- Smoking and alcohol consumption negatively impact sleep efficiency, while regular exercise enhances it.
- The Gradient Boosting Regressor model offers robust predictive accuracy for sleep efficiency.

## Future Work

- Explore additional features influencing sleep efficiency.
- Experiment with alternative machine learning algorithms to enhance prediction accuracy.
- Investigate the impact of different data preprocessing techniques on model performance.


## Usage

1. **Clone the Repository**:
   - Clone the project repository to your local machine using Git. You can do this by running the following command in your terminal or command prompt:

     ```
     git clone <repository_url>
     ```

2. **Install Dependencies**:
   - Navigate to the project directory and install the necessary Python libraries. You can use the provided `requirements.txt` file to install the required packages:

     ```
     pip install -r requirements.txt
     ```

3. **Run the Jupyter Notebook**:
   - Open the Jupyter notebook named `Sleep_Efficiency_Analysis.ipynb`.
   - Execute the cells in the notebook to reproduce the analysis, visualize the data, and train the machine learning model.
