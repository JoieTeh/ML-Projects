# ML-Projects

### Dataset Description:
The New York City High Volume For-Hire Vehicle Trip Records Dataset contains details about companies that conduct 10,000 + trips per day through their bases. The dataset contains information about the ride details encompassing, pricing, dates, times, distance, and other fees. It does not include any information about the locations, passenger or driver information. The dataset includes data from 2019, retrieved from the New York City Taxi & Limousine Commission (TLC). The 4 companies found in this dataset who are licensed under the High Volume For-Hire Service or who are currently in the application of becoming one include Juno, Lyft, Uber and Via. 

### Data Source and Links:
https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page
https://www.nyc.gov/assets/tlc/downloads/pdf/trip_record_user_guide.pdf


### Prediction and Forecast:
This project plans to predict the amount of tips paid (Column: tips) 

### Regression Method:
Linear Regression will be applied to investigate the correlation and relationship between variables

### Exploratory Data Analysis and Data Cleaning
Top 5 TLC Taxi Zone in which the trip began:
PULocationID
132    290795
138    283780
79     281696
61     237748
161    232599
Name: count, dtype: int64
#132  - Queens, JFK Airport
#138  - Queens, Laguardia Airport
#79   - Manhattan, East Village
#61   - Brooklyn, Crown Heights North
#161  - Manhattan, Midtown Center


Top 5 TLC Taxi Zone in which the trip ended:
DOLocationID
265    682678
132    353807
138    324068
61     247634
79     239739
#265 - LOCATION ID NOT FOUND
#132 -  Queens, JFK Airport
#138  - Queens, Laguardia Airport
#61  - Brooklyn, Crown Heights North
#79  -  Manhattan, East Village

As part of the EDA analysis, it was interesting to see the top five TLC taxi zones where trips began. They were Queens JFK Airport, Queens, LaGuardia Airport, Manhattan East Village, Brooklyn Crown Heights North and Manhattan Midtown Center. For trips that ended, the leading locations include 265 (unidentified location), 132 (Queens, JFK Airport), 138 (Queens, LaGuardia Airport), 61 (Brooklyn, Crown Heights North), and 79 (Manhattan, East Village). These locations reflect the busiest taxi zones, with JFK and LaGuardia airports being prominent origins and destinations.

Correlation of columns:

As for correlation of the data, it is understood that, 1 indicates a perfect positive correlation (as one variable increases, the other also increases), -1 indicates a perfect negative correlation (as one variable increases, the other decreases),  0 indicates no correlation.

<img width="385" alt="Screenshot 2024-12-11 at 4 26 13 PM" src="https://github.com/user-attachments/assets/c4cfc261-f204-417c-b865-f023bbec3dba" />

The analysis shows strong positive correlations between trip miles, trip time, base passenger fare, and driver pay, meaning that as these factors increase, driver pay tends to rise as well. BCF (Black Car Fund) also has a positive relationship with both driver pay and base passenger fare. On the other hand, some variables show weak negative correlations (e.g., -0.04), but these relationships are negligible and do not significantly affect the analysis.

Scatter Plot Diagram showing correlations between Distance Traveled and Drive’s Pay:

<img width="572" alt="Screenshot 2024-12-11 at 4 27 26 PM" src="https://github.com/user-attachments/assets/e053c62b-5d7b-4668-a45d-402372860c03" />


The correlation between trips miles traveled and driver pay is 0.94, indicating a very strong positive relationship. The scatter plot also confirms this, showing a clear upward trend: as the number of trips increases, driver pay rises significantly.

Scatter Plot Diagram showing correlations between Tips  and Drive’s Pay:
<img width="522" alt="Screenshot 2024-12-11 at 4 28 05 PM" src="https://github.com/user-attachments/assets/4c74879a-bdb9-45e8-8bbf-75037803bd15" />

The correlation between tips and driver pay is 0.34, indicating a moderate positive relationship. The scatter plot shows many data points clustered at 0, with a slight upward trend overall: as driver pay increases, tips tend to increase as well, but with some exceptions where customers choose to not pay any tips. This aligns with expectations, as tips are often calculated as a percentage of the total fare paid by customers.

Skewness and Histogram of Numerical Data Features:

Skewness of numerical columns:
PULocationID           -0.02
DOLocationID           -0.04
trip_miles              4.22
trip_time               2.15
base_passenger_fare     4.11
tolls                   5.01
bcf                     3.87
sales_tax               3.10
congestion_surcharge    0.37
airport_fee             3.36
tips                    5.73
driver_pay              3.56
dtype: float64

<img width="594" alt="Screenshot 2024-12-11 at 4 28 34 PM" src="https://github.com/user-attachments/assets/429e7eb9-b403-4ff6-b098-9d74500885f1" />


Some notable columns are trip_miles (4.22), base_passenger_fare (4.11), tolls (5.01), bcf (3.87), tips (5.73), and driver_pay (3.56). These columns are positively skewed, indicating that most values are concentrated at lower levels, with a long tail of higher values. This suggests that there are some trips with significantly higher miles, fares, tolls, tips, and driver pay that influence the average.

Box Plot of Driver Pay:
<img width="581" alt="Screenshot 2024-12-11 at 4 28 55 PM" src="https://github.com/user-attachments/assets/b36df8da-0cf2-4f3a-aaac-cc4e4200e3f0" />

The box plot for Driver’s Pay graphically shows the positive skewness of the data, indicating that the data has a long right tail with outliers. Given that pay values over $600 are significantly distant from the main distribution, it would be reasonable to consider these values as outliers. 

Box Plot of Base Passenger Fare:

<img width="568" alt="Screenshot 2024-12-11 at 4 29 11 PM" src="https://github.com/user-attachments/assets/0e4e57b8-0884-4f79-b6cd-a46d8069eeea" />


Next, the box plot for passenger fare also graphically shows the outliers. Given that fare values over $800 are significantly distant from the main distribution, it would be reasonable to consider these values as outliers and potentially drop those records. Removing outliers from both driver’s pay and base passenger fare can help the analysis remain representative of the typical range, reducing distortion in the predictive models.

One challenge that I might face during feature engineering is converting datetime values to categorical values to increase the value and predictive power of the data. As for data cleaning purposes, the two columns that contained null or na values were originating_base_num, on_scene_datetime columns, these data will not be needed to answer the initial hypothesis; thus deleting them was the most efficient way. It may also be useful to drop records where values in Driver Pay and Base Passenger Fare fall well outside the expected range, as extreme values could skew analysis results. Removing such outliers helps keep the data more consistent and representative of typical fares, ultimately leading to more accurate insights. *Lastly, during the feature engineering portion, I made the decision to drop the column access_way_flag, which had too few unique values.

### Feature Engineering and Modeling
Column name, Data type, and Feature engineering treatment

<img width="565" alt="Screenshot 2024-12-11 at 4 29 53 PM" src="https://github.com/user-attachments/assets/f585331b-3ea3-41ea-a26c-b05ef9ec22b2" />

### Model (Linear Regression) & Model Performance

Average metric [2.0906818852232956]

RMSE: 2.0895336513487557  R-squared:0.17273966681038655

For this milestone, I first indexed and encoded all of my data columns (feature engineering) to prepare my data for modeling. A challenge I faced throughout this project was the time it took to process all of my files as I was working with 5 years worth of data, and I would often have to re-do parts of my work because of the kennel crashing. Besides that, I realized how important getting your data ready thoroughly during the cleaning stage was. I realized that many of my data had nulls, not in the correct data type to perform functions on, or the records are not unique enough. For example, the column “wav_match_flag” had two values only “Y” and “N”, when I was indexing this column during feature engineering, it returned an error saying that there were no unique values remaining for indexing, as both 'Y' and 'N' were the only values in the column. Thus, there was a lot of back and forth between the cleaning and feature engineering process. Lastly, I also had trouble saving my files into the Trusted folder. The error returned said that I have a mismatch in data types for some of the columns and did not allow me to save it. I decided to drop the columns that returned errors and re-run the feature engineering code for the other columns, which allowed me to successfully save the code to my Trusted folder.

For the modeling portion, I applied linear regression to predict the tip values based on the vectorized columns. The code ran smoothly; however the model was weak. I also tried to produce visualizations however it took too long to transform my data into a Pandas DataFrame. The chart above shows the model prediction for the trip taxi data for the year of 2019. The Root Mean Square Error (RMSE) measures the average difference between values predicted by a model and the actual values. The value of RMSE is 2.08 which on average, the model’s predictions deviate from the actual tips by about $2.08, showing a weak prediction. Meanwhile, R-squared is a statistical measure used in machine learning to evaluate the quality of a regression model, it only returns a value of 0.17 which shows a low correlation with the dependent variables. The overall model returned would be considered a poor and weak model, especially where some tip values are negative which is unrealistic.

*Refer to jupyter notebook for model visualizations*

###  Summary & Conclusions

This project aimed to develop a predictive model for estimating taxi trip tips using features such as trip distance, time, fare, location, and other related attributes. By splitting the data into training and test sets, a machine learning pipeline and a linear regression model was used to estimate tips. The model’s performance was further evaluated using cross-validation metrics such as RMSE and R-squared to assess its accuracy. The results indicate that while the model captured some key relationships between features and tip amounts, there is room for improvement. Additionally, negative predicted tips emerged as an area of concern. This anomaly suggests a need to investigate whether such instances result from data quality issues, customer dissatisfaction, or general customer tipping behavior that was not captured in the data. Future iterations of this project could focus on several enhancements. First, more thoughtful feature engineering and exploration of a non-linear transformation could better reflect tipping patterns. Second, optimizing hyperparameters through a more comprehensive search could further enhance the model's predictive power. 

In conclusion, this project serves as a starting point for predicting tip amounts in taxi trips. While the current model demonstrates some predictive power, addressing its limitations through refined data preprocessing and parameter tuning could lead to a more robust and accurate picture. 





