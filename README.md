# Capstone-Project-EDA 🎬
---

## Table of Contents 📖
- [Project Overview](#project-overview)
- [About Dataset](#about-dataset)
- [Goal of the Project](#goal-of-the-project)
- [Data Sourcing](#data-sourcing)
- [Tools](#tools)
- [Data Cleaning/Preparation](#data-cleaning-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results/Findings](#results-findings)
- [Recommendation](#recommendation)
- [Limitation](#limitation)

### Project Overview
This project is about data cleaning and transformation to ensure quality by delving into the fascinating world of a data that includes 120 years (1896 to 2016) of Olympic games with information about athletes and medal results.
We focused on practicing the summary statistics and data visualization techniques that we've learned in the Udemy course.
![Olympic](https://github.com/MAishatLola/Capstone-Project-EDA-/assets/148435526/ede8b6c2-c2a4-40d3-a1ca-c19a6c8a6d93)


### About Dataset 
In general, this dataset is popular to explore how the Olympics have evolved over time, including the participation and performance of different genders, different countries, in various sports and events.
### Goal of the Project
- Examine/clean the dataset
- Explore distributions of single numerical and categorical features via statistics and plots
- Explore relationships of multiple features via statistics and plots
### Data Sourcing
Check out the original source if you are interested in using this data for other purposes [Download Here](https://www.kaggle.com/heesoo37/120-years-of-olympic-history-athletes-and-results)
### Tools 
- Python- Data Cleaning, Pivot_table and Visualization [Download Here](https://drive.google.com/file/d/1u2iy9xSvFOpngaP96g5bMNaKlClVnAaH/view?usp=sharing)

  
### Data Cleaning/Preparation

In the initial stage of data cleaning, we performed the following tasks:
1. Data Loading and Inspection
2. Handling and treatinng missing values
3. Handling the outliers
4. Pivot Table for summarization
5. Seaborn & Matplotlib for Data Visualization


### Exploratory Data Analysis
 - What are the average Age, Height, Weight of female versus male Olympic athletes?
   ```pd.pivot_table(olympics,  
               index='Sex',
               values=['Age', 'Height', 'Weight'],
              aggfunc='mean')
    ```
  ![Pivot table](https://github.com/MAishatLola/Capstone-Project-EDA-/assets/148435526/2f270dc1-b1d9-4495-8c8a-09b705fc0caf)

 - What are the minimum, average, maximum Age, Height, Weight of athletes in different Year?
    ```pd.pivot_table(olympics,
              index= 'Year',
              values= ['Age', 'Height', 'Weight'],
              aggfunc= ['min', 'mean', 'max'])
    ```
    ![pt](https://github.com/MAishatLola/Capstone-Project-EDA-/assets/148435526/b96e6562-59dc-4a5c-9848-0fe05bf2b053)
- What are the minimum, average, median, maximum Age of athletes for different Season and Sex combinations

    ```pd.pivot_table(olympics,
              index= ['Season', 'Sex'],
              values = 'Age',
              aggfunc= ['min', 'median', 'max'])
    ```
    ![pt2](https://github.com/MAishatLola/Capstone-Project-EDA-/assets/148435526/bbf1c75a-a4d2-4132-8545-d09500bcb60b)

- What are the average Age of athletes, and numbers of unique Team, Sport, Event, for different Season and Sex combinations

    ```pd.pivot_table(olympics,
              index= ['Season', 'Sex'],
              values = 'Age',
              aggfunc = 'mean',
              columns = ['Team', 'Sport', 'Event'])
    ```
![pt3](https://github.com/MAishatLola/Capstone-Project-EDA-/assets/148435526/1839cba1-ddf6-4c31-a5d4-7e5a9e9e5bcb)

- Is there and relationship between the weight and heights using the "Sex"?
    ```sns.relplot(olympics, x = 'Height', y = 'Weight', kind = 'scatter', hue = 'Sex', style = 'Sex')
    ```
    
![sns](https://github.com/MAishatLola/Capstone-Project-EDA-/assets/148435526/8ac9a2c2-d253-4489-b647-8a6da9b61ec5)
- Are there any correlation between the matrix of Age, Height, Weight?
    ```sns.heatmap(olympics[['Age', 'Height', 'Weight']].corr(), cmap = 'coolwarm')
    ```
  ![hm](https://github.com/MAishatLola/Capstone-Project-EDA-/assets/148435526/c2e9fbb5-b7ba-4549-9f83-2816d7bf7de3)



### Data Analysis

Some interesting codes/features we worked with:

```python

import seaborn as sns

sns.catplot(olympics, y = 'Year', hue = 'Sex', kind = 'count', col = 'Season');
```
### Results/Findings
The Analysis results are summarized as follows:


### Recommendations
Based on the Analysis conducted, these are the recommentions:


### Limitations
- Insufficient provisions of data for the size and representativeness of "Other" Gender Category

### References
Check out the original source if you are interested in using this data for other purposes [Download Here](https://www.kaggle.com/heesoo37/120-years-of-olympic-history-athletes-and-results)



