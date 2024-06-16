# Power-Data-Analysis-and-Exploration

**About Dataset**

The dataset consists of various electrical measurements taken at 15-minute intervals from December 4th to December 10th, 2023. Each row represents a timestamp with corresponding energy consumption data from multiple sources.

**Project Procedures and Result**

Introduction: This solution carefully analyses the CSV dataset provided using python as the programming language and google colab for notebook service. I have decided to use python due to its flexibility, libraries, ease of use and performance especially with time series datasets.

**Task 1 : Energy Consumption Data Conversion**

Procedures:

1)	I read the CSV file using pandas and I filtered the rows based on the provided dates (4th December and 7th December) and I saved the filtered rows as another dataframe.
   
2)	I excluded or filtered the date and timestamp columns from the list of columns to be converted to kWh, then I divided the new dataframe of energy usage only by 1000.

3)	Additionally, I calculated the total energy consumed within this time range using .sum() python syntax which resulted into a total of  15866kWh


**Task 2.1 :Consumption Analysis**

**Procedures:**

1)	Using .sum() syntax, I got the total energy sum for each column
   
2)	Using .nlargest(5) syntax, I got the highest 5 energy consumption rate equipments with A9,A7,A14,A15 and A13 topping the list in that order.
   
3)	The possible reasons for high energy usage in these circuits are :
   
•	availability of high power appliances in the areas where they are situated.

•	continuous or non-stop usage of these appliances as in the usage of air conditioners in homes and offices, computers, etc

•	the usage of heavy machinery as can be found in plantroom(A9) that has the highest record of energy usage.


**Task 2.2**

From the descriptive or summary statistics, it can be inferred that:

•	A9, having the highest energy usage has both the highest mean, minimum and maximum record usage per 15 mins

•	A14, despite being the 3rd on the list, has the highest variability (Standard deviation), indicating an ununiformity in the energy usage over time, this may be due to the usage of some heavy machines at some point.

•	A9 has outliers exemplifying extremely high energy consumption as shown in the boxplot.

**Task 3 : Off-Hours Energy Usage**

**Procedures:**

1)	I filtered the dataframe to only include off-hours period, period excluding 6am to 7am, Monday to Friday and the date and timestamp columns.

2)	I utilized the .sum() syntax on the filtered dataframe to calculate the total energy consumption

3)	I also evaluated the working hours energy consumption for comparison purpose (with off-hours)

4)	Off-hours energy usage totals 13219046Wh

5)	Working hours energy usage totals 18631351Wh

6)	Inference: The off-hours energy consumption is considerably high, meaning that some energy-consuming machines and operations are still on-going or in service even during the off hours.
   
**Task 4 : Peak Demand Analysis**

**Procedures:**

1)	I filtered the dataframe to exclude date and timestamp columns and summed the remaining columns horizontally using .sum(axis = 1), axis = 1 indicates summation horizontally across the columns.

2)	Then, I sort the resulting dataframe by total energy consumption in descending order.

3)	Searching for the top 10, using df_sorted(n=10) and print(peak_periods[[‘Date’, ‘Energy’]], I displayed the top 10 energy usage periods.

4)	energy usage and cost can be optimised by:

•	Shifting the using of heaving machines and power consuming activities to other periods

•	minimizing the activities done during these periods or restrict them to power-consuming activities alone, shifting moderately/low power-consuming activities to other periods.

•	diversification of source of energy and storing up of energy for peak periods.

**Task 5 :Trend Identification**

**Procedures:**

1)	Using subplot in matplotlib library, I derived a plot using trend of energy consumption across days.

2)	Inference: The observed trend indicates an almost uniform decrease in energy consumption between 2023-05 and 2023-08 and a substantial decrease towards 2023-09 and 2023-10. Generally, the energy consumption decreased across the days which may be due to reduction in the use of heavy machines and increased use of man power, or increased manual operation and less dependence on machinery operations. 

**Task 6 : Environmental Impact Estimation**

Procedures: 

1)	I calculated the total energy from the given CSV file  and multiplied it by 0.85( emission factor).
   
2)	26990595 kg CO2 per Wh is the total carbon footprint.




