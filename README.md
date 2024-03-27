# Exploratory-Data-Analysis-on-the-Car-Dataset
Uncover valuable insights within CAR DEKHO's car sales data, dissecting trends, and crafting strategic solutions to propel their business to greater heights.
1.)Domain/Topic knowledge:   
My dataset is cars selling prices and the features of the car.   
Form this dataset we can get to know  about the prices of the cars of different categories and there is 2059 different car data.  
Also every datapoint is about the sale of the car in India. So if any company want to know about the data of sales in india this dataset gives an understanding of the car industry in india.   
Selling Price:  
We can be familiarize with the selling prices of the car and the factors which affect the price of the car.   
performance and features:  
For comparing the performance and features of different car models based on their mileage, engine power, torque, etc.  
Trends in the used car market:   
The dataset includes cars from different years, which can be useful for analysing trends in the used car market.  
Fuel Efficient cars:   
The dataset provides information about the fuel type, which can be useful for analysing the popularity of different types of fuel-efficient cars.  
Knowledge on Indian car industry:   
Many companies want start their production in India specifically the electric cars. This data can be very useful for those companies to start their sales with the features that these cars have.  
  
  


Data Understanding:   
   
Make: Company of the car. It is categorical data which basically gives the company name  
Model: Name of the car. It is categorical data which tells the car's name.  
Price: Selling price of the car in INR. It is Numeric data but all are unique numerical values, it basically gives selling price of the car.  
Year: Manufacturing Year of the car. It is numeric data which gives year of manufacturing.  
Kilometer: Total kilometres Driven. It is numeric data.  
Fuel_Type: Fuel type of the car. It is ordinal data there are only three types of fuel 'Petrol', 'Diesel', 'CNG', 'LPG', 'Electric', 'CNG + CNG','Hybrid', 'Petrol + CNG', 'Petrol + LPG'.  
Transmission: Gear transmission of the car. It is ordinal categorical data. It has only two type of entries Manual, Automatic  
Location: City in which car is being sold. It is categorical data.  
Color: Color of the car. It is categorical data.  
Owner: Number of previous owners. It is categorical data, It has 'First', 'Second', 'Third', 'Fourth', 'Unregistered Car', '4 or More'.  
Seller_Type: it is a categorical value which have values like 'Corporate', 'Individual', 'Commercial Registration'.  
Engine: it is a numerical value which gives the horse power of  the car.  
Max_Power: it gives the maximum power of the engine and is a numerical data.  
Max_Torque: it gives information about maximum torque of the engine and it is numeric data.  
Drivetrain: it basically gives information of the cars drive train like 'FWD', 'RWD', 'AWD'.  
Length: it tells about the total length of the car horizontally. It is a numeric value.  
Width: it gives the information about width of the car horizontally it is a numeric data.  
Height: it tells information about height of the car from ground vertically and it is numeric data.  
Seating-Capacity: it gives the information about how many members can a car have at max. it is a numeric value.  
Fuel_Tank_Capacity: it gives information about total fuel tank capacity of the car it will be used for the maximum milage of the car. It is a numeric data.  
By seeing the above information we can get the all the information about the dataset I have chosen.      
  
Reasons:   
a car details dataset can serve a wide range of purposes, from helping individuals make informed car-buying decisions to supporting research, industry analysis, and regulatory efforts in the automotive domain.  
Car enthusiasts: Anyone can access car details datasets for various purposes, including building custom cars, tracking the value of collectible cars, or participating in motorsports.  
Educational Purposes: I am interested in data science, analytics, and statistical analysis so I choose this dataset for educational projects, classroom exercises, or research assignments.   
Curiosity on car sales: I have a great curiosity on cars and their features so I choose this dataset to basically understand about the car market in India and to know whether used cars can be used or the new ones.   
These are some reasons why I have chosen this dataset.   
   
   	   



 2.)Libraries Used and Aproaches: 
Numpy: 
"""numpy is used for numerical calculations in python""" EX: cars['Engine']=np.where(cars["Engine"].isna(),cars["Engine
"].median(),cars["Engine"]) Pandas: 
"""pandas is used for data preprocessing, data manipulation, specifically for spreadsheat data and also used to work with data frames, series""" Pandas provides two primary data structures - DataFrames and Series, which are highly versatile and allow for the representation and manipulation of structured data. 
 
EX: cars["Age"]=cars["Current_year"]-cars["Year"] cars.head(3) data manipulation: 
cars["Current_year"]=2023 
Data Import/Export: Pandas supports various file formats, such as CSV, Excel, SQL databases, and more, making it easy to read and write data from different sources. 
df=pd.read_csv("BlackFriday.csv")# Load data from a CSV file 
4. Data Manipulation: You can perform operations like filtering, sorting, merging, and reshaping data effortlessly, making it a crucial library for data wrangling tasks. # Extract numerical power values and RPM values cars['Power_bhp'] = cars['Max_Power'].str.extract(r'(\d+) bhp').astype(float) cars['Engine_RPM'] = cars['Max_Power'].str.extract(r'@ 
(\d+) rpm').astype(float) Matplotlib: 
"""matplotlib is used for plotting the graphs this library is specifically for data visualization purposes only""" 
 



Seaborn: 
"""Seaborn is based on matplotlib which does higher level visualizations which works on top of matplotlib to give plots more     interactive and particularly used for statistical and exploratory data analysis also it is good in integration with pandas.""" 
Seaborn is a visualization library that complements pandas and makes it easier to create aesthetically pleasing statistical graphics. It offers a high-level interface for drawing attractive and informative statistical graphics, making data visualization more accessible and allowing you to quickly explore and understand data patterns. 
1.Data Visualization: Seaborn specializes in statistical data visualization, offering a high-level interface for creating attractive and informative plots. sns.countplot(cars.Drivetrain) plt.title("Drive train Count") plt.xticks(rotation=100) plt.show() 
Statistical Plots: Seaborn provides a wide range of statistical plots, including scatter plots, bar plots, histograms, and regression plots, which are particularly useful for data exploration and analysis. 
categorical_columns = ["Make", "Fuel Type", "Transmission", "Location", "Color", "Owner", "Seller Type", "Drivetrain"] for col in categorical_columns:     sns.countplot(data=cars, x=col)     plt.figure(figsize=(10, 5))     plt.title(f"{col} Count")     plt.xticks(rotation=0)     plt.show() 
Categorical Data: It excels at handling categorical data, making it straightforward to create categorical plots like bar plots, box plots, violin plots, and swarm plots. 
Multivariate Analysis: It supports complex multivariate visualizations, such as pair plots and heatmap correlations, which are essential for understanding relationships between multiple variables. 
plt.figure(figsize=(10, 6)) correlation_matrix = cars.corr() sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm') plt.title('Correlation Heatmap') plt.show() 
 
Approaches followed: 
Data Cleaning: 
Check for missing values in each column and decide how to handle them (imputation or removal). 
Remove duplicates, if any, in the dataset. 
Ensure data consistency and accuracy. 
Data Summary: 
Calculate basic summary statistics (mean, median, standard deviation, etc.) for numerical columns like Price, Year, Kilometer, Engine, etc. 
For categorical columns like Make, Fuel_Type, Transmission, Location, Color, Owner, Seller_Type, and Drivetrain, summarize the frequency distribution of categories. 
Visualize data distributions and relationships. 
Data Visualization: 
Creating visualizations to understand the distribution of Price, Kilometer, Engine, and other numerical features. Histograms, box plots, and scatter plots are useful for this. 
Explore the relationships between categorical variables and the target variable (e.g., Price) using bar charts or violin plots. 
Analyze trends over time by visualizing Year against Price or other relevant attributes. 
Using pair plots or correlation matrices to identify relationships between numerical variables. Outlier Detection and Handling: 
           Identify outliers in numerical columns using box plots or scatter      plots. 
Decide whether to remove or transform outliers based on domain knowledge. 

Approaches for specific columns: 
For price column I removed the punctuation so that it will be integer data type so that I can do numeric analysis. 
For Engine column I removed the “cc” after every entry again to make it as int data type column. 
For maximum power and torque I divided the columns for better 
Understanding and I sorted the cars based on their power in bhp  
If power is equal for two cars then I checked the rpm if car1 is greater then it should come first. 
For removing null values first I tried capping the values with  median but that didn’t work as in the same rows other values are also missing so I tried to analyse the missing values Then I came to know that they are electric cars as these cannot be in this dataset as this dataset contains only fuel based cars in more proportion. 
I dropped all the electric vehicles  they are approximately 25 cars in the dataset. 
After I was searching for the null values in fuel capacity column but a mysterious fact has been unveiled that 29 BMW cars are not having tank capacity information so I deleted all the 29 rows. 
  
3.)EDA: 
EDA stands for Exploratory Data Analysis. It is a critical step in the data analysis process that involves examining and visualizing data to summarize its main characteristics, often with the help of statistical graphics and other data visualization techniques. The primary goal of EDA is to gain insights into the data, discover patterns, detect anomalies, and formulate hypotheses for further analysis. 
Outcomes of CARS DATA EDA: 
To get more insights from the data and  uncover the underlying patterns in the data like: 
Finding relationships between the car sales area wise, the factors which effect the car sale price e.t.c Quality of this Dataset: 
1.)Model of the car should be 3 words so for the correct prediction it is important 
2.)Engine, Max_Power, Max_Torque, Drivetrain, Length, Width, Height, Seating_Capacity, Fuel_Tank_Capacity these columns has null values in the dataset 
3.)There are some cars which have null values in specified columns above so these can be removed. 
4.) in engine column the entries are with cc but for analysis it is not required and calculations get wrong as it is string type. 
So I the data quality in this dataset is not upto the mark for data analysis and EDA. 
4.) Some Questions and their answers for Analysis. 
 1.What is the average selling price of the cars in the dataset?     cars.Price.mean() 
1718279.036819637 
2.What is the most common fuel type used in the cars? 
Diesel=954 
Percentage of most common fuel type is: 50.907150480256135 % 
3.What is the average fuel tank capacity of the cars in the dataset? 
Average fuel tank capacity in litres of the cars in the dataset is:  
52.21734258271077 
4.What is the average engine capacity of the cars in the dataset? 
average engine capacity of the cars in the dataset is :  1682.82924226254 
5.What is the average number of seats in the cars? 
5.295090715048025 
6.What is the most common seller type in the dataset? 
array(['Corporate', 'Individual', 'Commercial Registration'], dtype=object) 
 
7. What is the most common transmission type in the cars? Manual       1037 
Automatic     837 
8.What is the average age of the cars in the dataset? 
For this question there is no direct answer beacause there is no direct column representing age of the car in the 
dataset so we need to create age column, but what is the year this dataset is updated? for this we need the maximum year in the year column so we will apply max function on that and make it as the current year and we subtract the year from the current year so that we can get the age 
6.286552828175027 
What is the most common brand of cars in the dataset 
It is obvious from the figure that "Maruthi Suzuki" is the common among all the companies it is almost 20.23% among all the values 
What is the average distance covered by the cars in the dataset? 
The average kilometers driven for the cars in this dataset is "53178.13980789755" 
What is the most common owner type in the cars? 
First               1504 
Second               322 
Third                 30 
UnRegistered Car      18 Name: Owner, dtype: int64 
from the figure we can say that first owner cars are more in the dataset and it is obvious only first 
owner cars sell more than any other type of cars 
   
  
What is the average maximum power of the cars in the dataset? So from this data the average maximum power of cars is "129.09423503325942" 
What is the average torque of the cars in the dataset? 
69.0 
What is the most expensive car in the dataset? 35000000 
It is obvious from the dataset "ferrari 488 GTB" is the highest selling price in this dataset 
What is the cheapest car in the dataset? 
In the dataset the minimum selling price price of all cars is 49000 and it is Tata Nano Base 
What is the most powerful car in the dataset? 
the ferrari 488 GTB is the most powerful car in this dataset 
What is the least powerful car in the dataset? 
Make                           Toyota 
Model                 Fortuner 3.0 MT 
Price                         1000000 
Year                             2010 
Kilometer                      127000 
Fuel_Type                      Diesel 
Transmission                   Manual 
Location                     Guwahati 
Color                           White 
Owner                           Third 
Seller_Type                Individual 
Engine                           2982 
Max_Power                    171@3600 
Max_Torque                   343@1400 
Drivetrain                        AWD 
Length                         4695.0 
Width                          1840.0 
Height                         1850.0 
Seating_Capacity                  7.0 
Fuel_Tank_Capacity               80.0 
Current_year                     2023 
Age                                13 
Power(bhp)                        NaN 
Engine(RPM)                       NaN 
Torque (Nm)                       NaN 
RPM                               NaN 
Power_bhp                         NaN 
Engine_RPM                        NaN 
Name: 2036, dtype: object 
 
 	 
What is the most common model of cars in the dataset? X1 sDrive20d xLine                       15 
Which columns in the dataset directly impact on the resale of the cars? 
From the heat map we can see that power(bhp) is the column that has highest impact on selling price of the car 
What is the most common fuel type used in the cars? 
from the statistics we can see that Diesel is the most common fuel type in the dataset that is almost 954 out of 1874 are of diesel and it is almost 50.9% of all the cars in the dataset. 
 	 
Hypothesis Testing:
For this I have assumed one hypothesis and have done all the tests that are 
T-Test, F-Test, Z-Test, Chi- Squared test.
Hypothesis:
The average price of diesel cars is significantly different from the average price of petrol cars.
These are the results from those tests that are evident that my hypothesis is true.
T-test
T-Statistic: 6.843165463479428
P-Value: 1.0699683749158076e-11
The difference in average prices is statistically significant.
The results indicate that there is a statistically significant difference in the average prices between diesel and petrol cars. The low p-value (close to zero) suggests strong evidence against the null hypothesis¶
F-test:
F-Statistic: 47.372131553562454
P-Value: 8.052339105325683e-12
There is a significant difference in average prices between Diesel and Petrol cars.
Z-test:
Z-Statistic: 6.882741572481309
P-Value: 5.871148223101824e-12
There is a significant difference in average prices between Diesel and Petrol cars.
The Z-test assumes a known population standard deviation, which is often not the case in practice. The t-test is more commonly used when the population standard deviation is unknown.
Chi- Squared Test:
Chi-Square Statistic: 68.9082187336131
P-Value: 6.845717174801284e-13
There is a significant association between Fuel Type and Transmission.

These all tests have their P-values less than 0.05 so these tests prove that there is significant difference in prices of the diesel and petrol cars.

Conclusion:
All conducted tests consistently suggest that there is a significant difference in average prices between Diesel and Petrol cars. Additionally, there is a significant association between Fuel Type and Transmission. These findings provide statistical evidence to support the initial hypothesis that there are significant variations in prices and associations with transmission types between Diesel and Petrol cars. 
The t-test and ANOVA were both suitable and produced consistent results.
The Chi-Square test was appropriate for assessing the association between Fuel Type and Transmission.
Considering the consistency of results and the nature of your analysis, either the t-test or ANOVA is a suitable choice for comparing average prices between Diesel and Petrol cars.

