LungCapData Visuals
This project focuses on exploring and visualizing a dataset related to lung capacity, which includes columns such as age, height, smoking habits, gender, and cesarean birth. Various visualizations such as histograms, boxplots, scatter plots, and heatmaps are generated to understand relationships in the data.

Table of Contents
Introduction

Dataset

Installation

Usage

Visualizations

License

Introduction
This notebook provides various visualizations for the LungCapData dataset. The dataset includes data on lung capacity, age, height, smoking habits, gender, and cesarean birth. The purpose of the notebook is to explore the relationships between these variables and gain insights from the data through visualizations.

Dataset
The dataset consists of the following columns:

LungCap: Lung capacity (in liters)

Age: Age of the individual

Height: Height of the individual

Smoke: Whether the individual smokes or not

Gender: Gender of the individual

Caesarean: Whether the individual had a cesarean birth

You can download the dataset from Kaggle.

Installation
To run this notebook, you need to have the following Python libraries installed:

Matplotlib for plotting.

Seaborn for statistical data visualization.

Pandas for data manipulation and analysis.

You can install the necessary libraries by running:

bash
Αντιγραφή
Επεξεργασία
pip install matplotlib seaborn pandas
Usage
Clone or download the repository.

Install the required dependencies listed above.

Open the Jupyter notebook to start exploring the data and running visualizations.

Steps to Use the Code:
Load Data: The dataset is loaded into a Pandas DataFrame:

python
Αντιγραφή
Επεξεργασία
import pandas as pd
df = pd.read_csv('lung_capacity.csv')
Data Cleaning: Check for missing values and handle them if necessary:

python
Αντιγραφή
Επεξεργασία
df.isnull().sum()
Visualization: The notebook generates various visualizations to explore the relationships between the variables.

Histogram with KDE (Kernel Density Estimate):

python
Αντιγραφή
Επεξεργασία
import seaborn as sns
import matplotlib.pyplot as plt

sns.histplot(df['Age'], kde=True, bins=20, hue='Gender')
plt.title('Age Distribution with Gender Hue')
plt.show()
Boxplot:

python
Αντιγραφή
Επεξεργασία
sns.boxplot(x='Gender', y='Age', data=df)
plt.title('Age Distribution by Gender')
plt.show()
Scatter Plot:

python
Αντιγραφή
Επεξεργασία
plt.scatter(df['Age'], df['Height'], s=df['LungCap']*10, c=df['LungCap'], cmap='cool', alpha=0.6)
plt.title('Height vs Age with Lung Capacity')
plt.colorbar(label='Lung Capacity')
plt.show()
Heatmap of Correlation:

python
Αντιγραφή
Επεξεργασία
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.title('Correlation Heatmap')
plt.show()
Interpretation: After visualizing the data, interpret the results to understand the relationships between variables.

Visualizations
The following visualizations are included:

Histogram with KDE: Shows the distribution of age, with a KDE curve and hue based on gender.

Boxplot: Displays the distribution of age by gender.

Scatter Plot: Visualizes the relationship between age and height, with the size of points representing lung capacity.

Heatmap: Shows the correlation between the numeric variables (Age, Height, LungCap).
