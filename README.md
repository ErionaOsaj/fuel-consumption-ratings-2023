# Fuel Consumption Ratings 2023 - Data Preprocessing and Visualization - FIEK 2023/2024

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

### Outlier and skewness etection using IQR (Boxplots)  

Outliers can significantly impact our analysis, leading to skewed results. Detecting and handling these is crucial for maintaining the integrity of our findings.

We used boxplots to visualize and detect outliers in our numerical data. Here's how we did it:

- `plt.boxplot(dataset['Engine Size (L)'], showmeans=True)`: This command generates a boxplot for the 'Engine Size (L)' column and shows the mean value. The boxplot provides a visual summary of the central tendency and dispersion of the data, as well as potential outliers.
  
  The following values were extracted from the 'Engine Size (L)' boxplot:
  - Median: The middle value of the dataset when it is ordered from least to most.
  - Mean: The average of the dataset, indicating central tendency.
  - Minimums: The lowest value within the range that is not considered an outlier.
  - Maximums: The highest value within the range that is not considered an outlier.

- `extract_boxplot_values(bp)`: This custom function extracts and prints the median, mean, minimum, and maximum values from the boxplot object. It uses the matplotlib `boxplot` object to access the statistical properties of the plotted data.

Here is an example of boxplot:
<img width="422" alt="image" src="https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/27639068/032eca42-0bab-4c23-a631-37eef46ab8ab">

Any detected outliers were further investigated to determine whether they were the result of data entry errors or other inaccuracies. If an outlier was determined to be inaccurate, it was corrected if possible or removed to prevent it from distorting our analysis.

To understand the distribution of fuel consumption among the vehicles in our dataset, we visualized the 'Fuel Consumption (L/100Km)' using a boxplot and extracted key statistical values.

Generate a boxplot for the 'Fuel Consumption (L/100Km)' with the mean indicated
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
```

Median (5.0 L/100Km): The data's midpoint, with half of the vehicles being more efficient and the other half less so.
Mean (5.23649 L/100Km): Slightly higher than the median, indicating the small right skew.
Minimum (3.0 L/100Km) and Maximum (8.0 L/100Km): Represent the typical range of highway fuel consumption.
![Alt text](image-1.png)

........
### Skewness

Skewness is a statistical metric that gives us an idea of the symmetry, or lack thereof, in the data distribution. The skewness coefficient is a single numerical value that reflects the shape of the distribution of values in a dataset.

Example: We calculate the skewness for the 'Cylinders' feature in our dataset as follows:
```python
skewness = dataset['Cylinders'].skew()
print(f"Skewness coefficient: {skewness}")
```
The skewness value gives us an indication of the asymmetry level in the distribution:

- **Approximately Symmetric Distribution**:
  - A skewness value between -0.5 and 0.5 means the distribution is approximately symmetric.

- **Moderately Skewed Distribution**:
  - A skewness value between -1 and -0.5 indicates moderate negative skewness (left-skewed).
  - A skewness value between 0.5 and 1 indicates moderate positive skewness (right-skewed).

- **Highly Skewed Distribution**:
  - A skewness value less than -1 indicates a highly negative skewness (left-skewed).
  - A skewness value greater than 1 indicates a highly positive skewness (right-skewed).


From boxplots and from function that displays skewness we can see that some of our data are skewed :
- **Engine Size (L)** - Right-skewed
  - Skewness coefficient: 1.0260918957977176
  - Interpretation: The majority of vehicles have smaller engines, with fewer vehicles having larger engines.

- **Cylinders** - Right-skewed
  - Skewness coefficient: 1.3003254083126115
  - Interpretation: Most vehicles have a lower number of cylinders, with fewer vehicles having a higher number of cylinders.

- **Fuel Consumption (L/100Km)** - Right-skewed
  - Skewness coefficient: 0.6917887375909869
  - Interpretation: Vehicles generally have lower fuel consumption, with fewer instances of high fuel consumption.

- **Hwy (L/100 km)** - Right-skewed
  - Skewness coefficient: 0.883049860122652
  - Interpretation: The distribution of highway fuel consumption is such that most vehicles are more fuel-efficient, with some exceptions having high consumption rates.

- **Comb (L/100 km)** - Right-skewed
  - Skewness coefficient: 0.7340232375008856
  - Interpretation: The combined fuel consumption metric also shows a right-skew, indicating a concentration of vehicles with lower consumption values.

- **CO2 Emissions (g/km)** - Slightly right-skewed
  - Skewness coefficient: 0.63581867933566
  - Interpretation: The CO2 emissions show a slight right-skew, implying a larger concentration of vehicles with emissions on the lower end.

- **CO2 Rating** - Slightly right-skewed
  - Skewness coefficient: 0.02460774858363436
  - Interpretation: This near-zero skewness suggests that the CO2 Rating is almost symmetrically distributed.

- **Smog Rating** - Left-skewed
  - Skewness coefficient: -0.8602475026142282
  - Interpretation: The Smog Rating distribution leans towards higher values, with a tail extending towards the lower end.

### Multivariate statistics

Correlation analysis is essential for understanding the relationships between different variables in a dataset. In our vehicle dataset, we explore how different metrics such as engine size, fuel consumption, and emissions ratings are interrelated. The following heatmap visualizes the correlation matrix, providing a color-coded representation of the correlation coefficients.

#### Insights from the Correlation Heatmap

![image](https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/27639068/ef008bc2-8507-4d4c-8cd9-e3504909e2c9)


*Figure: Heatmap of correlation coefficients between vehicle metrics.*

The heatmap allows us to quickly grasp the strength and direction of relationships:

- **Positive Correlations (Red tones)**: These indicate a direct relationship where an increase in one variable tends to be associated with an increase in another. For example, 'Cylinders' show a strong positive correlation with 'CO2 Emissions (g/km)', suggesting that vehicles with more cylinders tend to emit more CO2.

- **Negative Correlations (Blue tones)**: These signify an inverse relationship where an increase in one variable tends to be associated with a decrease in another. A notable example is between 'CO2 Rating' and 'Fuel Consumption (L/100km)', indicating that vehicles with a better CO2 rating typically consume less fuel.

- **Neutral Correlations (White tones)**: Near-zero values suggest no significant linear relationship between the variables.

##### Key Observations:

- 'Engine Size (L)' correlates strongly with 'Cylinders' and fuel consumption-related metrics, implying that larger engines are generally less fuel-efficient and produce higher emissions.

- 'CO2 Rating' has a notably strong negative correlation with fuel consumption and emissions metrics. This inverse relationship highlights that as fuel efficiency improves, CO2 ratings tend to be higher, denoting a lower environmental impact.

- 'Smog Rating' shows a moderate negative correlation with engine-related metrics, suggesting that higher engine sizes and fuel consumption could lead to lower smog ratings.

By understanding these correlations, we can better prepare our data for modeling and infer which features might be most significant in predicting vehicle emissions and efficiency.

### Visualization of Z-Score Outliers in Engine Size Distribution

In our data preprocessing steps, we've included an analysis of outliers within the 'Engine Size (L)' feature of our dataset. To identify these outliers, we've utilized the Z-score method. The following visualization aids in understanding the distribution of 'Engine Size (L)' and highlights the outliers detected through Z-scores.

![image](https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/27639068/a2f03513-02b5-4bfa-bba9-eb75d30fc164)


*Figure: Engine Size (L) Distribution with Z-Score Outliers.*

#### Interpretation of the Visualization:

- **Data Points (Blue dots)**: Represent the engine sizes of individual vehicles within the dataset plotted against their index.

- **Mean (Red dashed line)**: Depicts the average engine size across the dataset.

- **Standard Deviation Regions**:
  - **Within 1 STD (Yellow shaded area)**: Encompasses 68% of the data points, indicating one standard deviation from the mean.
  - **Within 2 STD (Green shaded area)**: Covers 95% of the data points, indicating two standard deviations from the mean.
  - **Within 3 STD (Blue shaded area)**: Represents 99.7% of the data points, indicating three standard deviations from the mean.

- **Outliers (Red dots)**: These are the data points that lie beyond 3 standard deviations from the mean. These outliers are potential candidates for further scrutiny or removal to improve the robustness of subsequent analyses.

The function `plot_z_score_distribution_remove_outliers` is responsible for generating this plot and removing outliers. It calculates Z-scores for the specified property (`Engine Size (L)` in this case), marks the mean and standard deviation intervals, and highlights outliers. This visual representation is crucial in making informed decisions about outlier treatment, which is a key step in ensuring the quality of our dataset for modeling purposes.


### Outlier Removal

We have performed outlier detection based on the statistical analysis conducted earlier form the boxplots and from using z-score for rows that have too many outliers. Outliers were identified as values that fall outside the range defined by our boxplot analysis.

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
```
### Outlier Removal Results

After applying our outlier detection criteria, we observed the following changes to our dataset:

- **Original Dataset Size**: 833 rows.
- **Dataset After Outlier Removal**: 818 rows.


## Phase 3 : Data Visualization
We will utilize various Python libraries for data visualization, including but not limited to:
- Matplotlib
- Seaborn
- Pandas
- Plotly
- Ipywidgets (interact)

Some of our visualization goals include:
- Exploring the distribution of fuel consumption across different vehicle classes.
- Analyzing the relationship between engine size, fuel consumption, and CO2 emissions.

### Vizualization according to datatypes

#### Countplots

A count plot is a type of bar chart that shows the frequency of items in different categories. In our project, we utilized a count plot to visualize the distribution of vehicles across various vehicle classes. This type of plot is particularly beneficial for categorical data where we want to compare the size of each category against others. We used countplots also for other categorical data but here we explain as example only for vehicle classes.

Key reasons for using a count plot in our analysis:

1. **Simplicity and Clarity**: Count plots provide a straightforward visual summary of the data, showing the count of observations in each categorical bin using bars.

2. **Comparison**: It allows for immediate comparison of the frequency between different categories. For instance, it can easily show which vehicle class is the most or least frequent in the dataset.

3. **Data Quality Checks**: It helps in identifying data imbalances or anomalies, such as a class with unusually high or low counts, which might indicate data collection biases or errors.

4. **Communication**: Count plots are widely recognized and understood, making them an excellent choice for communicating findings to a general audience.

##### Count of Vehicles by Vehicle Class

The count plot visualizes the distribution of vehicles across different classes, as extracted from the 2023 fuel consumption ratings dataset. The x-axis categorizes vehicles into full-size, SUVs (small, standard), compact, minicompact, two-seater, subcompact, station wagon (small, mid-size), pickup trucks (small, standard), minivan, and special purpose vehicles. The y-axis shows the number of vehicles in each category.

From the count plot, we can observe that standard SUVs and small station wagons have the highest count, indicating their popularity or prevalence in the dataset. On the other hand, special purpose vehicles and small pickup trucks are less common.

This visualization is particularly useful for identifying the most and least common vehicle types, which can inform market trends and potential focus areas for environmental efficiency improvements. It is created using a count plot, which is an excellent tool for displaying categorical data frequencies. The varying colors help in distinguishing between the different vehicle classes at a glance.

![image](https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/27639068/b7547c26-e00d-4c1f-8390-b245c0f1e665)

 Here is the code descripiton
 
 ```python
plt.figure(figsize=(10, 6)) # Set the size of the plot for better readability.
sns.countplot(x='Vehicle Class', data=dataset) # Create a count plot using seaborn library. The 'x' parameter specifies the column for which we want to show the counts.
plt.title('Count of Vehicles by Vehicle Class') # Add a title to the plot.
plt.xticks(rotation=45) # Rotate the x-axis labels by 45 degrees for better visibility of the labels.
plt.ylabel('Count') # Label the y-axis as 'Count'.
plt.xlabel('Vehicle Class') # Label the x-axis as 'Vehicle Class'.
plt.show() # Display the plot.
```
#### Piecharts

A pie chart is a circular statistical graphic divided into slices to illustrate numerical proportion. In our project, we use a pie chart to represent the relative proportions of different vehicle classes within the dataset. This visualization provides an immediate visual cue about the share of each class, making it an effective tool for displaying the data composition.

Key reasons for using a pie chart:

1. **Proportion Visualization**: It provides a quick and easy way to compare the proportion of each vehicle class in the dataset. Each slice's size is proportional to the quantity it represents.

2. **Intuitive for Composition**: Pie charts are particularly useful when you want to show a simple proportion of data points within a whole, highlighting segments like market share or production percentages.

3. **Aesthetic Appeal**: They are visually appealing and can be easily understood by a wide audience, which makes them an excellent choice for presentations and summary reports.
   
##### Distribution of transmission types

he pie chart titled "Distribution of Transmission Types" provides a visual breakdown of the various transmission types present within the vehicle dataset. Each segment of the pie chart corresponds to a type of vehicle transmission: Automatic, Manual, Continuously Variable (CVT), and Automated Manual/Sequential.

Key Insights from the pie chart:

- **Automated Manual/Sequential** transmission is the most prevalent type, constituting over half of the dataset, shown by the largest segment at 52.8%.
- **Automatic** transmission types are also significant, making up 27.8% of the dataset.
- **Continuously Variable (CVT)** transmissions account for a smaller portion of 11.4%.
- **Manual** transmissions are the least common in this dataset, at 8.1%.

<img width="390" alt="image" src="https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/27639068/a3cd5702-7754-4f87-b18b-97b2d8ed2584">

#### Boxplot Analysis

The boxplot is a powerful tool for visualizing the central tendency and dispersion of data. In this case, it is used to compare the CO2 emissions across different fuel types, which can be instrumental in environmental impact assessments, policy-making, and strategic planning for emission reductions.

##### CO2 Emissions by Fuel Type

The figure titled "CO2 Emissions by Fuel Type" is a boxplot that provides a statistical summary of the distribution of CO2 emissions for different fuel types, identified here as Z, X, D, and E.

Key components of the boxplot:

- **Central rectangle (the "box")**: Represents the interquartile range (IQR), showing the middle 50% of the data. The bottom and top of the box are the first (Q1) and third (Q3) quartiles, and the band inside the box is the median (Q2).
- **Whiskers**: Indicate variability outside the upper and lower quartiles, extending to the minimum and maximum values within 1.5 * IQR from the Q1 and Q3. Points outside this range are often considered outliers.
- **Color differentiation**: Each box is colored differently to visually separate the fuel types.

Analysis of the boxplot:

- Fuel type Z shows a wide IQR indicating significant variability in emissions, with a median above 250 g/km.
- Fuel type X has a slightly smaller IQR, suggesting less variability, and a lower median than Z, indicating generally lower emissions.
- Fuel types D and E have similar IQRs, which are narrower than Z and X, indicating less variability in emissions. Both have medians substantially lower than Z and X, which suggests these fuel types may be more efficient or cleaner-burning.

![image](https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/27639068/3f30f1f5-96b1-493b-99a1-4e1de324bd82)

Here is an example of how such a boxplot can be generated using Python's matplotlib library:

```python
plt.figure(figsize=(10, 6))
sns.boxplot(x='Fuel Type', y='CO2 Emissions (g/km)', data=dataset)
plt.title('CO2 Emissions by Fuel Type')
plt.xlabel('Fuel Type')
plt.ylabel('CO2 Emissions (g/km)')
plt.show()
```

#### Histogram with Kernel Density Estimate (KDE)

A histogram with a Kernel Density Estimate (KDE) provides a detailed view of data distribution, combining the specificity of a histogram with the smoothness of a KDE curve. The histogram illustrates the data's frequency within bins, while the KDE offers a smooth curve that represents the overall density and trends in the data. This dual visualization approach allows for an intuitive understanding of the data's structure, highlighting both the distribution's granularity and its underlying patterns.

#### Distribution of Smog Rating

The figure titled "Distribution of Smog Rating" depicts a histogram overlaid with a kernel density estimate (KDE) curve. This graph is designed to show the frequency distribution of smog ratings in the dataset.

Key features of the histogram:

- **Bars**: Represent the frequency of vehicles within each smog rating category. The height of each bar corresponds to the number of vehicles that fall into each rating bin.
- **KDE Curve**: The smooth line that traverses the plot is a KDE curve, which estimates the probability density function of the smog rating variable. It helps to identify the distribution shape and the central tendency visually.

Interpretation of the histogram:

- The histogram bars indicate the number of vehicles that have received each smog rating score, providing a visual representation of the distribution.
- The KDE curve suggests that there are peaks at certain smog ratings, indicating common values where a higher number of vehicles are rated.
  
![image](https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/27639068/282ade61-ee38-4b28-922b-948113971a10)

The code to generate this histogram with KDE is as follows:

```python
# Initialize the figure with a specified size for better visibility
plt.figure(figsize=(10, 6))

# Create a histogram with a kernel density estimate (KDE) overlay
# 'bins' determine the number of divisions in the data range
# 'kde=True' adds the Kernel Density Estimate plot on top of the histogram
sns.histplot(dataset['Smog Rating'], bins=30, kde=True)

# Set the title of the histogram for context
plt.title('Distribution of Smog Rating')

# Label the x-axis with the variable of interest
plt.xlabel('Smog Rating')

# Label the y-axis with 'Frequency' to denote the count of occurrences
plt.ylabel('Frequency')

# Display the plot on the screen
plt.show()
```

### Multidimensional, static and interactive vizualization

#### Scatter plots 

##### Fuel Consumption vs. CO2 Emissions Scatter Plot

The scatter plot above illustrates the relationship between fuel consumption (measured in liters per 100 kilometers) and CO2 emissions (measured in grams per kilometer) for a variety of vehicles. Each point on the plot corresponds to a single vehicle, with the point's color representing the engine size (in liters) according to the color scale on the right. Larger and warmer-colored points indicate vehicles with larger engines. The plot shows a clear trend: as fuel consumption increases, CO2 emissions tend to rise, which is consistent with larger-engine vehicles generally consuming more fuel and emitting more CO2.

<img width="476" alt="image" src="https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/27639068/39accd52-501c-4a0a-9ab3-e8d6143e711e">

#### Polar plot 


##### Comparison of Vehicles by Fuel Consumption and CO2 Emissions

This polar plot offers a comparison of various vehicle classes based on their fuel consumption and CO2 emissions. Each segment's radial distance from the center represents fuel consumption, while the angular position indicates the level of CO2 emissions. Different symbols and colors are used to distinguish between vehicle classes, such as full-size, SUVs (small and standard), compacts, and more. This type of visualization is useful for observing trends and outliers in multidimensional data, allowing for an at-a-glance comparison of how different vehicle classes stack up in terms of environmental impact. The plot is interactive and you can filter by vehicle class.

The essence of this visualization is to explore the relationship between a vehicle's fuel consumption and its CO2 emissions while also considering the vehicle's engine size and class. It provides a multidimensional view of the data, where you can observe the following:
Clusters: Groupings of similar vehicle types based on fuel consumption and emissions.
Outliers: Any vehicles with particularly high or low values for these metrics.
Trends: For example, if larger vehicles (like full-size SUVs) tend to consume more fuel and emit more CO2, which would appear as a cluster of larger symbols further from the center of the plot.

- The angular axis (represented by the circle's degrees) correlates with CO2 emissions. Each vehicle's emissions level positions it at a certain angle along the circumference, effectively categorizing vehicles by emissions in a circular layout.
- The radial distance from the center of the plot to a data point corresponds to the vehicle's fuel consumption. The further a point is from the center, the higher the fuel consumption of that vehicle.
- Distinct shapes and colors represent different vehicle classes, enabling quick visual differentiation. For instance, diamonds may represent SUVs, while squares may represent compact cars. The color coding further aids in distinguishing between subcategories within these classes, like small versus standard SUVs.

Such a plot is especially useful for identifying patterns and outliers in the data. For instance, if larger vehicles such as full-size cars and standard pickup trucks are clustered towards the outer edge of the plot, this indicates higher fuel consumption. In contrast, more fuel-efficient vehicle classes would be closer to the center.

<img width="466" alt="image" src="https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/27639068/57dac434-8b4c-4008-a4fb-8cd019ebb1d8">

####  t-SNE visualization

t-SNE visualization clusters vehicles by make based on high-dimensional data, effectively reducing the complexity to two dimensions while preserving the local structure of the dataset. This technique ensures that similar vehicles are represented by points close together, while dissimilar ones are farther apart. The plot is a powerful tool for pattern recognition and outlier detection, revealing the natural groupings within the vehicle dataset according to their characteristics such as engine size, cylinders, fuel consumption, and CO2 emissions.
This is interactive vizualization where you can filter data based on all categorical data.

![image](https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/27639068/3d570761-fcbb-4e0e-9c42-81a50b0d7b30)

#### 3d Scatter plots

##### 3D Scatter Plot of Engine Size, CO2 Emissions, and Cylinders

The figure is a 3D scatter plot providing a multi-dimensional view of vehicles' engine size, CO2 emissions, and the number of cylinders. Each axis represents one of these three variables: the 'x' axis shows engine size (L), the 'y' axis represents CO2 emissions (g/km), and the 'z' axis indicates the number of cylinders. Points are colored according to fuel type, with each color representing a different fuel type such as Z, X, D, or E. This visualization technique allows for an in-depth analysis of how these variables interact with each other and how they are distributed across different fuel types. It serves as a valuable tool for identifying trends and correlations in automotive data, which can inform design and environmental considerations.

<img width="468" alt="image" src="https://github.com/ErionaOsaj/fuel-consumption-ratings-2023/assets/27639068/4ad55d25-b96d-4365-9cac-2ced418174c0">

## Tools and Environment
We have used Jupyter Notebook for the analysis and visualization.
The analysis is performed using Python v3.11.5.
The required libraries (Pandas, Matplotlib, Seaborn) are included in the Anaconda distribution. 


## Additional Resources
- [Fuel Consumption Ratings Search Tool](https://www.nrcan.gc.ca/energy-efficiency/energy-efficiency-transportation/fuel-consumption-guide/21185)
- [More Information on Fuel Consumption Testing](https://www.nrcan.gc.ca/energy-efficiency/energy-efficiency-transportation/fuel-consumption-guide/21185)

## References
- [Original Dataset on Kaggle](https://www.kaggle.com/datasets/imtkaggleteam/fuel-concumption-ratings-2023)

We hope this Jupyter Notebook helps you explore and analyze the dataset effectively. Feel free to reach out to any of the team members for questions or further assistance.
