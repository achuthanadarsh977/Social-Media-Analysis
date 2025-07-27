Objective
This task aims to help students explore, analyze, and visualize a real-world dataset containing
social media behavior. By the end of this task, students will:
 Load and clean structured data using Python
 Perform exploratory data analysis (EDA)
 Create insightful visualizations
 Summarize key behavioral patterns
 Present real-life user case studies
The goal is to encourage students to build analytical thinking and present findings in an
interpretable manner.


Tools Required

Tool Purpose

Google Colab: Cloud-based Python coding environment

Pandas: Data loading and cleaning

seaborn, matplotlib.pyplot: Data visualization

Numpy: Mathematical operations

Getting Started with Google Colab

1. Open https://colab.research.google.com
2. Click on New Notebook (top-left corner)
3. Rename your notebook as Week2_SocialMediaAnalysis
4. To upload the CSV file:
o Click the folder icon on the left sidebar
o Click the upload icon and select social_media_usage_1000.csv
o Once uploaded, your file will be in /content/

Use the path /content/social_media_usage_1000.csv when reading the file in your code.

굇굃굈굉굊 Dataset Overview
File: social_media_usage_1000.csv
Each row represents a user's social media behavior. Key columns include:
 User_ID, Gender, Age, Location
 Instagram_hrs, Facebook_hrs, YouTube_hrs
 Purpose (e.g., Education, Entertainment, Work)
 Device_Type (Desktop, Mobile, Tablet)
 Daily_Sessions

脥� Step-by-Step Guide (With Sample Code)
▪ Step 1: Load the Dataset
Use pandas to load the CSV file into a DataFrame. This is the first step to accessing and
exploring your data.
import pandas as pd

# Load the dataset
df = pd.read_csv("/content/social_media_usage_1000.csv")
# Preview the first five records

print(df.head())
# Display info about columns and data types
print(df.info())

▪ Step 2: Data Cleaning
Before analyzing, clean the data by handling missing values:
# Fill missing values
# Gender - fill with mode
df['Gender'].fillna(df['Gender'].mode()[0], inplace=True)

# Age - fill with median
df['Age'].fillna(df['Age'].median(), inplace=True)

# Platform hours - fill with mean
for col in ['Instagram_hrs', 'Facebook_hrs', 'YouTube_hrs']:
df[col].fillna(df[col].mean(), inplace=True)

# Purpose - fill with placeholder
df['Purpose'].fillna('Unknown', inplace=True)

▪ Step 3: Feature Engineering
Create a new column to represent total time spent on social media:
# Create Total_Hours column
df['Total_Hours'] = df[['Instagram_hrs', 'Facebook_hrs', 'YouTube_hrs']].sum(axis=1)
This helps compare overall usage patterns.

舊舉 Data Visualizations (Expected Output)

I generated these plots to support insights. Below each plot is a sample
explanation of how to approach it.

Average Time per Platform
Use mean() on each platform column and plot a bar chart using seaborn.
# Sample approach:
# - Calculate average for each platform using df.mean()
# - Use sns.barplot() to show platform vs hours

Gender-wise Total Usage
것겄겅겆겇 Group the data by gender and use a boxplot to compare distribution of Total_Hours.
# Sample approach:
# - Plot sns.boxplot() with Gender on X-axis and Total_Hours on Y-axis
# - Add title and label

Age vs Total Usage
것겄겅겆겇 Use scatterplot to check if age influences social media time.
# Sample approach:
# - Use sns.scatterplot() with Age and Total_Hours
# - Add hue for Gender, style for Device_Type


4. Location-wise Usage
것겄겅겆겇 Group data by Location and use barplot to compare average usage.
# Sample approach:
# - Use groupby('Location') and mean() on Total_Hours
# - Visualize with sns.barplot()

5. Purpose-wise Usage
것겄겅겆겇 Compare Total_Hours across different purposes using a boxplot.
# Sample approach:
# - Use sns.boxplot() with Purpose on X-axis and Total_Hours on Y-axis
# - Rotate x-labels for better visibility
6. Device Type vs Sessions
것겄겅겆겇 Use boxplot to compare number of sessions across device types.
# Sample approach:
# - Use sns.boxplot() with Device_Type and Daily_Sessions







Learning Outcomes
By the end of this project, i learnt how to:
 Handle real-world CSV datasets using pandas
 Clean missing or noisy data
 Create new features from existing data
 Visualize data trends using seaborn/matplotlib
 Interpret real-world usage patterns
 Present insights and user case studies visually


