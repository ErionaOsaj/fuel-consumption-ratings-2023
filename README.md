# Fuel Consumption Ratings 2023 - Data Preprocessing and Visualization 

## Overview
This project is developed as a part  of the Master studies curriculum at the Faculty of Electrical and Computer Engineering (FIEK). It focuses on the essential aspects of data preprocessing and visualization, key areas in the field of data science and analytics.

## Objective
The primary objective of this project is to demonstrate comprehensive skills in handling, processing, and visualizing data. It encompasses various techniques and methodologies pertinent to cleaning, transforming, and interpreting data effectively.

## Team Members
- Eriona Osaj
- Edon Budakova
  
## Introduction
This dataset contains model-specific fuel consumption ratings and estimated carbon dioxide emissions for new light-duty vehicles available for retail sale in Canada. The data has been adjusted to reflect 5-cycle testing, making it easier to compare vehicles from different model years. It includes information on various vehicle attributes and their environmental impact, which can be used to make informed decisions about fuel-efficient vehicles.

## Dataset Description
The dataset contains the following columns:
1. **Year:**
   - The model year of the vehicle, indicating when it was manufactured.

2. **Make:**
   - The brand or manufacturer of the vehicle.

3. **Model:**
   - The specific model name or designation of the vehicle.

4. **Vehicle Class:**
   - The category or type of the vehicle (e.g., sedan, SUV, truck) based on its intended use and design.

5. **Engine Size (L):**
   - The displacement of the vehicle's engine, measured in liters (L). the volume of fuel and air that can be pushed through a car's cylinders.
          
6. **Cylinders:**
   - The number of cylinders in the vehicle's engine. This is an important factor in determining the engine's power and efficiency.

7. **Transmission:**
   - The type of transmission system used in the vehicle, specifying how power is transmitted from the engine to the wheels.

8. **Fuel Type:**
   - The type of fuel that the vehicle uses (e.g., gasoline, diesel, electric).

9. **Fuel Consumption (L/100Km):**
   - The amount of fuel consumed by the vehicle per 100 kilometers traveled. It provides a measure of fuel efficiency.City       and highway fuel consumption ratings are shown in litres per 100 kilometres (L/100 km) - the combined rating (55% city,      45% hwy)
     
10. **Hwy (L/100 km):**
    - The highway fuel consumption rating, representing the vehicle's fuel efficiency on the highway.

11. **Comb (L/100 km):**
    - The combined fuel consumption rating, representing the vehicle's overall fuel efficiency in a mix of city and highway driving.

12. **Comb (mpg):**
    - The combined fuel consumption rating in miles per gallon (mpg). It provides an alternative measure of fuel efficiency.

13. **CO2 Emissions (g/km):**
    - The tailpipe emissions of carbon dioxide (in grams per kilometre) for combined city and highway driving. It indicates the environmental impact of the vehicle.

14. **CO2 Rating:**
    - The tailpipe emissions of carbon dioxide rated on a scale from 1 (worst) to 10 (best).

15. **Smog Rating:**
    - The tailpipe emissions of smog-forming pollutants rated on a scale from 1 (worst) to 10 (best).

## Data Preprocessing
In this Jupyter Notebook, we will perform the following data preprocessing steps:
1. Data Cleaning: We will check for and handle missing values and inconsistencies in the dataset.
2. Data Formatting: We will format columns to ensure consistency and ease of analysis.
3. Data Transformation: We may create new features or transform existing ones to better suit our analysis and visualization.

## Dataset Attributes

**Categorical Attributes:**

_Nominal:_
- Make
- Model
- Vehicle Class
- Transmission
- Fuel Type

_Ordinal:_
- CO2 Rating
- Smog Rating

**Numerical Attributes:**

_Interval:_
- Year

_Ratio:_
- Engine Size (L)
- Cylinders
- Fuel Consumption (L/100 km)
- Hwy (L/100 km)
- Comb (L/100 km)
- Comb (mpg)
- CO2 Emissions (g/km)

## Data quality
In our effort to ensure the highest data quality for our analysis, we conducted an extensive examination of the dataset. Below are our key findings and the methodologies applied in each aspect of data quality assessment.

### Noise and Unexpected Values

- **Noise in 'Year' Column**: Unusual non-year values were detected in the 'Year' column using `dataset['Year'].unique()`. Found entries include 'Understanding the table', 'Model', 'Transmission', 'Fuel type', 'Fuel consumption', 'CO2 emissions', 'CO2 rating', 'Smog rating'.
- **Noise in 'Make' Column**: We identified unexpected values in the 'Make' column with `dataset['Make'].unique()`. These include specific emissions information, fuel types, and transmission details such as 'the tailpipe emissions of carbon dioxide (in grams per kilometre) for combined city and highway driving', 'M = manual', '3 – 10 = Number of gears', 'X = regular gasoline', 'Z = premium gasoline', 'D = diesel', 'E = ethanol (E85)', 'N = natural gas'.

> **Note**: The exploration for outliers will be conducted in Phase 2 of our project.

### Missing Values

- **Detection and Strategy**: We detected missing values in various columns using `dataset.isnull().sum(axis=0)`. The findings are as follows:
  - Year: 15 missing values
  - Make: 2 missing values
  - Model: 23 missing values
  - Vehicle Class: 23 missing values
  - Engine Size (L): 23 missing values
  - Cylinders: 23 missing values
  - Transmission: 23 missing values
  - Fuel Type: 23 missing values
  - Fuel Consumption (L/100Km): 23 missing values
  - Hwy (L/100 km): 23 missing values
  - Comb (L/100 km): 23 missing values
  - Comb (mpg): 23 missing values
  - CO2 Emissions (g/km): 23 missing values
  - CO2 Rating: 23 missing values
  - Smog Rating: 23 missing values
  
![image](https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/44554983/29bb55b1-3b3f-4258-aa30-069e43d71637)

### Duplicate Records
- **Duplicate Check**: We verified that there are no duplicate records in our dataset using the `dataset.duplicated().sum()` function, ensuring the uniqueness and integrity of our data.

![image](https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/44554983/c11e818a-eed0-4e27-9d21-34b92af9cb80)

## Data Integration
In our project, data integration plays a pivotal role in ensuring that we have a comprehensive and unified dataset for analysis. 

- **Single Source Integration**: Our dataset is sourced exclusively from Kaggle, which simplifies the integration process. The dataset encompasses extensive information about vehicle fuel consumption ratings and emissions, making it a valuable resource for our analysis. We imported the dataset into our analytical environment using the following command:

  ```python
  dataset = pd.read_csv('Data/fuel-consumption-ratings-2023.csv', encoding='ISO-8859-1')

## Aggregation
In our dataset, we've implemented several aggregation techniques to distill and comprehend the data more effectively. These aggregations help in summarizing the dataset and provide us with insights into CO2 emissions and fuel consumption patterns:

- **CO2 Emissions by Make**: We summarized the CO2 emissions data by the make of the vehicle. This aggregation allows us to observe which makes of vehicles tend to have higher or lower emissions on average.

- **CO2 Emissions by Fuel Type**: We analyzed the CO2 emissions according to the type of fuel used. This helps us understand the emission levels associated with different types of fuel, from gasoline to electric variants.

- **Fuel Consumption by Make**: We aggregated fuel consumption data by the vehicle's make, providing an average fuel consumption figure for each manufacturer. This is a crucial indicator of the efficiency and performance of different makes.

- **Fuel Consumption by Fuel Type**: The dataset was also aggregated to show fuel consumption based on fuel type. It helps in comparing the efficiency of vehicles running on different fuel sources.

The purpose of these aggregations is to:
- Simplify the dataset by reducing the number of attributes or objects, making the data more manageable.
- Adjust the scale of analysis from individual vehicles to broader categories such as make and fuel type.
- Achieve more stable and less variable data, which can be advantageous for identifying broader trends and making informed decisions.

Through these aggregated views, we gain a better understanding of the environmental impact and efficiency of vehicles, which is instrumental in driving forward our analysis and subsequent findings.

## Sampling
Sampling is a fundamental technique in data analysis, typically employed when dealing with large datasets. It enables statisticians and data analysts to perform preliminary investigations and derive conclusions without processing the entire dataset, which can be prohibitively expensive or time-consuming.

In the context of our project:

- Given our dataset comprises only 865 rows, full sampling is not essential for the preliminary or final analysis stages. The manageable size of our dataset allows us to conduct comprehensive examinations without the need to sample.
- This advantageously positions us to utilize the complete dataset, providing the benefit of drawing insights from every available data point and ensuring that our analysis encompasses all the nuances and patterns present.
- As such, we have opted to leverage the entire dataset for our analysis, ensuring that no detail, however minor, is overlooked in our pursuit of accuracy and depth in our findings.

We recognize the value of sampling in larger datasets and are prepared to implement this technique should the scope of our data expand in the future. For now, our focus remains on making the most of the detailed and rich dataset at our disposal.

## Data Cleaning
During our data cleaning process, we focused on enhancing the dataset's clarity and relevance by addressing entries with missing or irrelevant information.

- **Eliminating Irrelevant Entries**: Specific entries contained data that were irrelevant or did not make sense, such as erroneous entries in the 'Year' and 'Make' columns. We identified these entries as noise in our data.

- **Handling Rows with Null Values**: In instances where rows contained null values and coincided with the noisy data identified, we decided to remove these rows entirely from our dataset. This was done to ensure that our analysis would only be based on complete and accurate information.

Here is the approach we used to clean our dataset:
- We removed rows that had nonsensical values in 'Year' and 'Make' columns, which also contained null values across other attributes. This step was necessary to ensure the remaining data was free of noise and errors.
  
![image](https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/44554983/cb0cfb31-fe3a-44e4-8ff6-b753c08f4de1)

## Dimensionality Reduction
In the data preprocessing phase, we have also performed dimensionality reduction to simplify our model without losing important information.

### Redundant Feature Removal
Some features in our dataset were found to be redundant, providing no additional information.
- **Year Column Removal**: All entries in our dataset are from the year 2023; therefore, this feature does not provide any variance and has been dropped.

### Discretization and Binarization
To enhance model performance and interpretability, we categorized engine sizes into discrete bins:
- **Binning engine size into two categories**
  
![image](https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/44554983/ddb1d788-2b50-4df3-a5b0-2bc7f7a4b9a0)

### Transformation
We applied normalization to the CO2 emissions data to prepare for machine learning algorithms:

- **Normalize CO2 emissions data**:
  
![image](https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/44554983/2f3a5db1-fbec-49d3-be20-e498cc1d23e7)





## Phase 2: Outlier Detection and Data Exploration

In this phase, we focused on identifying and managing outliers, correcting inaccurate discoveries, and conducting a thorough exploration of the dataset, including summarizing statistics and multivariate analysis.

### Outlier Detection

Outliers can significantly impact our analysis, leading to skewed results. Detecting and handling these is crucial for maintaining the integrity of our findings.

We used boxplots to visualize and detect outliers in our numerical data. Here's how we did it:

- `plt.boxplot(dataset['Engine Size (L)'], showmeans=True)`: This command generates a boxplot for the 'Engine Size (L)' column and shows the mean value. The boxplot provides a visual summary of the central tendency and dispersion of the data, as well as potential outliers.
  
  The following values were extracted from the 'Engine Size (L)' boxplot:
  - Median: The middle value of the dataset when it is ordered from least to most.
  - Mean: The average of the dataset, indicating central tendency.
  - Minimums: The lowest value within the range that is not considered an outlier.
  - Maximums: The highest value within the range that is not considered an outlier.

- `extract_boxplot_values(bp)`: This custom function extracts and prints the median, mean, minimum, and maximum values from the boxplot object. It uses the matplotlib `boxplot` object to access the statistical properties of the plotted data.

For the 'Engine Size (L)', we observed the following:
Median Mean Minimum Maximum

- Similarly, for the 'Cylinders' data: Median Mean Minimum Maximum

### Addressing Inaccuracies

Any detected outliers were further investigated to determine whether they were the result of data entry errors or other inaccuracies. If an outlier was determined to be inaccurate, it was corrected if possible or removed to prevent it from distorting our analysis.

To understand the distribution of fuel consumption among the vehicles in our dataset, we visualized the 'Fuel Consumption (L/100Km)' using a boxplot and extracted key statistical values.

```python
# Generate a boxplot for the 'Fuel Consumption (L/100Km)' with the mean indicated
bp = plt.boxplot(dataset['Fuel Consumption (L/100Km)'], showmeans=True)
![Alt text](image.png)

We used extract_boxplot_values(bp) to retrieve the median, mean, minimum, and maximum from the boxplot:

Median (12.1 L/100Km): Splits the dataset in half.
Mean (12.4315 L/100Km): Indicates the average, suggesting a right skew.
Minimum (4.4 L/100Km) and Maximum (21.3 L/100Km): Mark the range of typical values.

### Highway Fuel Consumption Analysis

To examine highway fuel efficiency, we plotted a boxplot for 'Hwy (L/100 km)' with the code:

```python
bp = plt.boxplot(dataset['Hwy (L/100 km)'], showmeans=True)

Median (5.0 L/100Km): The data's midpoint, with half of the vehicles being more efficient and the other half less so.
Mean (5.23649 L/100Km): Slightly higher than the median, indicating the small right skew.
Minimum (3.0 L/100Km) and Maximum (8.0 L/100Km): Represent the typical range of highway fuel consumption.
![Alt text](image-1.png)

........

### Outlier Removal

We have performed outlier detection based on the statistical analysis conducted earlier. Outliers were identified as values that fall outside the range defined by our boxplot analysis.

```python
# Determine the number of rows that have outlier values
number_of_rows = dataset[<various outlier conditions>].shape[0]

# Print the number of outliers detected
print(f"Number of outliers detected: {number_of_rows}")

# Calculate the total number of rows in the original dataset
print(f"Original dataset contained {dataset.shape[0]} rows.")

# Identify indices of outliers for removal
outliers_index = dataset[<various outlier conditions>].index

# Remove the outliers from the dataset
dataset.drop(outliers_index, inplace=True)

# Print the new number of rows after outliers have been removed
print(f"Dataset after dropping outliers contains {dataset.shape[0]} rows.")

### Outlier Removal Results

After applying our outlier detection criteria, we observed the following changes to our dataset:

- **Original Dataset Size**: 833 rows.
- **Detected Outliers**: 140 rows.
- **Dataset After Outlier Removal**: 693 rows.

The removal of 140 outliers significantly reduced our dataset size. This step is crucial for the accuracy of our project, as it ensures that our dataset does not include data points that are far outside the expected range. Cleaning the dataset from these outliers allows us to conduct a more reliable and representative statistical analysis in the later stages of our project.

## Data Visualization
We will utilize various Python libraries for data visualization, including but not limited to:
- Matplotlib
- Seaborn
- Pandas

Our visualization goals include:
- Exploring the distribution of fuel consumption across different vehicle classes.
- Analyzing the relationship between engine size, fuel consumption, and CO2 emissions.
- Visualizing trends in fuel consumption and emissions over the years.

## Tools and Environment
We have used Jupyter Notebook for the analysis and visualization.
The analysis is performed using Python v3.11.5.
The required libraries (Pandas, Matplotlib, Seaborn) are included in the Anaconda distribution. 
```

## Additional Resources
- [Fuel Consumption Ratings Search Tool](https://www.nrcan.gc.ca/energy-efficiency/energy-efficiency-transportation/fuel-consumption-guide/21185)
- [More Information on Fuel Consumption Testing](https://www.nrcan.gc.ca/energy-efficiency/energy-efficiency-transportation/fuel-consumption-guide/21185)

## References
- [Original Dataset on Kaggle](https://www.kaggle.com/datasets/imtkaggleteam/fuel-concumption-ratings-2023)

We hope this Jupyter Notebook helps you explore and analyze the dataset effectively. Feel free to reach out to any of the team members for questions or further assistance.
