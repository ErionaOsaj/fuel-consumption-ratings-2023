# Fuel Consumption Ratings 2023 - Data Preprocessing and Visualization

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
   - The amount of fuel consumed by the vehicle per 100 kilometers traveled. It provides a measure of fuel efficiency.

10. **Hwy (L/100 km):**
    - The highway fuel consumption rating, representing the vehicle's fuel efficiency on the highway.

11. **Comb (L/100 km):**
    - The combined fuel consumption rating, representing the vehicle's overall fuel efficiency in a mix of city and highway driving.

12. **Comb (mpg):**
    - The combined fuel consumption rating in miles per gallon (mpg). It provides an alternative measure of fuel efficiency.

13. **CO2 Emissions (g/km):**
    - The estimated amount of carbon dioxide (CO2) emitted by the vehicle per kilometer traveled. It indicates the environmental impact of the vehicle.

14. **CO2 Rating:**
    - A rating assigned to the vehicle based on its CO2 emissions. It is often part of environmental labeling initiatives.

15. **Smog Rating:**
    - A rating assigned to the vehicle based on its emissions that contribute to smog. It is often part of environmental labeling initiatives.
    
## Data Preprocessing
In this Jupyter Notebook, we will perform the following data preprocessing steps:
1. Data Cleaning: We will check for and handle missing values and inconsistencies in the dataset.
2. Data Formatting: We will format columns to ensure consistency and ease of analysis.
3. Data Transformation: We may create new features or transform existing ones to better suit our analysis and visualization.

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
