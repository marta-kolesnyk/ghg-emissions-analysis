# Analysis of GHG Emissions due to Agriculture Production

## Overview: 
The production of agriculture and food involves the emission of greenhouse gases (GHG), which are responsible for the climate change. Environmental organizations constantly monitor the level of the emissions across all countries to make sure they comply with the regulations and to implement new policies where needed.

## Objective:
This project aims to analyze worldwide emissions from agriculture and establish the relationship between the emission levels and economic indicators to help environmental organizations implement new policies.

## Data: 
Initially 3 datasets were used for this project:
- Greenhouse gas emissions
- Temperature changes
- Population

Later on, data was enriched with the next datasets:
- Agriculture production export and import
- GDP (Gross Domestic Product)
- Gross production value of agriculture
 
All data was obtained from FAOSTAT – the statistics division of Food and Agriculture Organization of the United Nations (FAO), and is available here: https://www.fao.org/faostat/en/#data.

**Data cleaning and analysis was conducted using Python programming language in Jupyter Notebook.**

## Data Cleaning Process and Challenges:
- Unnecessary columns were dropped, and all of the columns were renamed to keep the consistensy.
- Datasets were checked for duplicates (none found), columns were checked for mixed-type data, and missing values. Records with missing values were removed as they were less than 5% of the dataset.
- Descriptive statistics was calculated for each dataset and no unrealistic/unusual values were found.
- The datasets were merged on three key columns: 'Country Code', 'Country', 'Year'. 
- **CHALLENGE:** Categorical values were transposed into separate columns. Here is code snippets:
![Screenshot 2024-04-15 180344](https://github.com/marta-kolesnyk/ghg-emissions-analysis/assets/152204235/acd36e7d-f4f1-4c42-94b0-b9e0a4b6746d)
![Screenshot 2024-04-15 180441](https://github.com/marta-kolesnyk/ghg-emissions-analysis/assets/152204235/3ab489b7-22dd-4ed1-a0d6-69cc6f37fa79)
![Screenshot 2024-04-15 180459](https://github.com/marta-kolesnyk/ghg-emissions-analysis/assets/152204235/9df18173-2036-4529-b4dc-a8e15917f6cb)

- Final dataframe had 3,755 records and 14 variables.

## Exploratory Analysis:
- Built a heatmap to check the correlation between all variables and created a pairplot to visualize the relationship between variables.
- Made hypotheses based on the correlation findings:
**First hypothesis:** Countries with large population release more emissions.
**Second hypothesis:** Total GHG emisisons couse bigger temperature chenges in 4 years.
- Built a linear regression model for Agriculture Gross Production Value and Total Emissions. This model was not a good fit for these variables, as the mean squared error was very large, and predicted results differed a lot from the actual ones, even though the R2 was 0.87.
- Conducted cluster analysis:
  - created a subset of a dataframe without categorical values
  - standardized the data
  - applyed elbow technique to determine the number of clusters
  - used k-means model for clustering
  - built scatterplots for multiple pairs of variables to see how data is grouped
- Conducted time-series analysis for yearly emissions subset.

## Findings:
- Countries can be grouped into tree clusters based on the macroeconomic and emission data: one cluster - China, second - U.S., India, China, third - other countries.
- Countries from the first two clusters are in the list of top-10 countries by GHG emissions.
- Countries with higher GDP per capita show decreasing trend in emission amount.

## Project Deliverables:
- Tableau Storyboard
- Jupyter Notebook Scripts
