# ExcelBikeBuyersDashboard
# Bike Buyers Dataset

This dataset has details of 1000 users from different backgrounds and whether or not they buy a bike. Some NA (Null / Empty) values are injected in the dataset. 

## Columns -

- **ID:** Numeric and unique values
- **Marital Status:** Categorical values namely, *Married* and *Single*
- **Gender:** Categorical values namely, *Male* and *Female*
- **Income:** Numeric values
- **Children:** Numeric values
- **Education:** Categorical values namely, *Partial Highschool, Highschool, Partial College, Bachelors* and *Graduate Degree*
- **Occupation:** Categorical values namely, *Manual, Skilled Manual, Clerical, Professional* and *Management*
- **Home Owner:** Categorical values namely, *Yes* and *No*
- **Cars:** Numerical values
- **Commute Distance:** Categorical values namely, *0-1 Miles, 1-2 Miles, 2-5 Miles, 5-10 Miles* and *10+ Miles*
- **Region:** Categorical values namely, *Europe, Pacific* and *North America*
- **Age:** Numerical values 
- **Purchased Bike:** Categorical values namely, *Yes* and *No*

## Data Cleaning

**Missing Values (Numeric):** Missing values of the numeric columns were low relative to the one thousand rows of data. The missing cells in Income (6 blanks), Children (8 blanks), Cars (9 blanks) and Age (8 blanks) were replaced with the mode.



**Missing Values (Categorical):** Missing values of the categorical columns were also low relative to the dataset. The missing cells in Marital Status (7 blanks), Gender (11 blanks) and Home Owner (4 blanks) were replaced with the Most Frequent Value.

Mode/Most Frequent Value representing the central or typical value in the column helped preserve the central tendency of the dataset. As compared to the mean, mode was not affected by the outliers in the numerical columns. Since the missing values were relatively low, the distribution of dataset was maintained.

**Grouping Data:** The numerical data in the Income and Age columns spans across a diverse range of values. To tackle the data in an organised manner, the data was grouped into new columns accordingly. The grouping of the data was in the following manner:


|**Income Category**|**Income**|
| - | - |
|Low|$10,000 - $30,000|
|Lower-Middle|$30,001 - $60,000|
|Upper-Middle|$60,001 - $100,000|
|High|$100,001 +|


|**Age Category**|**Age**|
| - | - |
|25-34|Young Adult|
|35-49|Adult|
|50-64|Middle-Aged|
|65+|Senior|

## Data Visualisation

Pivot tables were used across three new worksheets to create visualisations surrounding key metrics such as age, income, gender, etc. These worksheets served as the working area to give way to the dashboard.

1. **Bar Chart (Marital Status):**  How does the count of bike purchases vary among different marital statuses? Are married individuals more likely to purchase bikes?

The interactive bar chart with filters available to select marital status and bike purchase shows that single people are more likely to purchase bikes by a very small margin. On the contrary, married people are more likely not to purchase bikes. This result can also be accounted for the fact that our customer dataset is tilted heavily towards married customers, who make up 54% of the data.

2. **Bar Chart (Gender):** Build a bar graph to compare the count of male and female customers. Does gender influence bike purchases, and if so, to what extent?

The interactive bar chart with filters available to select gender and bike purchase shows that bike purchase based on gender was negligible. At the same time, male customers are more likely not to purchase bikes. 

3. **Histogram (Income):** What income distribution among bike buyers? Are there specific income brackets that show a higher likelihood of bike purchases?

Based on the histogram visualisation, the lower middle-income category shows the highest likelihood of bike purchase followed by upper middle-, low- and high-class categories.

4. **Histogram (Age):** Create a histogram to understand the age distribution of bike buyers. Are certain age groups more inclined to purchase bikes?

Based on the histogram visualisation, the adult age category purchases the most bikes, followed by the middle-aged and young adults. The senior age category ranks last as it dips to just 17 purchases, barely reaching 10% of bike purchases.

5. **Box Plot (Income):** Identify outliers in the income distribution of bike buyers. Are there any extreme income values, and how might they impact purchasing behaviour?

The green box plot shows the income distribution of bike buyers. While outliers are present in all three income boxplots (overall customers, customers who purchased bikes, and customers who did not purchase bikes), the median value is maintained across the three boxplots. 

The fact that the lower quartile of bike-purchasing customer income is about $10,000 higher compared to the other two suggests that individuals with higher incomes are more likely to purchase bikes. The presence of a lower upper whisker for bike purchasing customer income (about $30,000 lower) indicates that individuals with lower incomes may be less likely to purchase bikes.

6. **Pie Chart (Region):** Represent the distribution of bike purchases by region using a pie chart. Are there regions where bike purchases are notably higher?

The bike purchasing region of North America shows a heavy majority of 46%, followed by 31% of bike purchases from Europe and the rest 23% from the Pacific.

7. **Scatter Plot (Income vs. Age):** Create a scatter plot to investigate the relationship between income and age. Do individuals with higher incomes tend to be in specific age groups?

The income steadily increases for young adults, reaching a peak for adults before it slowly dips as it pushes into the middle adult category and reaches a steady low for senior customers. The adult age group (35-49) have the highest income.

8. **Stacked Bar Chart (Marital Status & Gender):** How does the distribution of bike purchases differ when considering both marital status and gender simultaneously? Are there notable patterns?

The stacked bar chart shows that single people are more likely to purchase bikes. Single women and married men purchase more bikes than their marital status counterparts. 

9. **Correlation Heatmap (Numeric Variables):** Use a heatmap to visualize the correlation matrix between numeric variables. What variables show a strong correlation, and how might this influence purchasing behaviour?

Income shows a weak positive correlation with both the number of children (0.25) and age (0.17), suggesting that individuals with higher incomes may have more children and be slightly older. 

A moderate positive correlation between income and cars (0.43) indicates that higher-income individuals are more likely to own more cars. The number of children is moderately positively correlated with age (0.52), suggesting older individuals tend to have more children. 

Additionally, a weak positive correlation between age and the number of cars (0.18) implies a slight tendency for older individuals to own more cars. 

These correlations provide insights into potential associations. Correlation does not imply causation, and other factors may influence these relationships.

10. **Pair Plot (Subset of Variables):** Create a pair plot for a subset of variables (e.g., Income, Age, Children). Are there clear relationships between these variables, and how might they impact bike purchases?


A pair plot is not directly possible in Excel because it does not have built-in functions specifically for pair plots. The pair plot in the dashboard was created by grouping individual scatterplots. There are no considerable relationships observed between the variables.

11. **Pie Chart (Occupation):** Represent the distribution of bike purchases by occupation using a pie chart. Are there occupations where bike purchases are notably higher?

The professional occupation (31%) occupies the highest percentage of bike buyers, closely followed by skilled manual occupation (24%), clerical (18%), management (15%) and manual (12%) at the least. 

12. **Bar Chart (Commute Distance):** What is the distribution of bike commutes across different categories?

The 0-1 miles category has the highest count, crossing the 350 counts. The other categories remain roughly stable below 200, with the 10+ miles category dipping to 111 counts at the lowest.

## Challenges:
No significant challenges were faced during this project as the dataset was relatively small and could be managed and manipulated in Excel without any lags. The data analysis toolkit had to be enabled to create a correlation heatmap for variables. On similar lines, the pair plot had to be manually made using scatterplots, which proved to be time-consuming compared to using Python or R, thus highlighting the limitations of Excel analysis and visualisations.

## Conclusion:

Single individuals, particularly single women and married men emerge as more likely buyers, while the married segment shows a lower inclination. Income plays a pivotal role; notably, the lower middle-income category exhibits the highest likelihood of making such purchases. Age-wise, adults dominate the buyer demographic, while seniors contribute the least. Regional trends indicate North America as the primary market for bikes. Factors like occupation and commute distance also play discernible roles in shaping purchasing behaviour. These insights, derived from comprehensive visualizations and correlations, provide valuable guidance for targeted marketing strategies and business decisions in the bike industry.
