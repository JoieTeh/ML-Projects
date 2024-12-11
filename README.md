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
# 265 - LOCATION ID NOT FOUND
#132 -  Queens, JFK Airport
#138  - Queens, Laguardia Airport
#61  - Brooklyn, Crown Heights North
#79  -  Manhattan, East Village

As part of the EDA analysis, it was interesting to see the top five TLC taxi zones where trips began. They were Queens JFK Airport, Queens, LaGuardia Airport, Manhattan East Village, Brooklyn Crown Heights North and Manhattan Midtown Center. For trips that ended, the leading locations include 265 (unidentified location), 132 (Queens, JFK Airport), 138 (Queens, LaGuardia Airport), 61 (Brooklyn, Crown Heights North), and 79 (Manhattan, East Village). These locations reflect the busiest taxi zones, with JFK and LaGuardia airports being prominent origins and destinations.

Correlation of columns:

As for correlation of the data, it is understood that, 1 indicates a perfect positive correlation (as one variable increases, the other also increases), -1 indicates a perfect negative correlation (as one variable increases, the other decreases),  0 indicates no correlation.

<img width="385" alt="Screenshot 2024-12-11 at 4 26 13 PM" src="https://github.com/user-attachments/assets/c4cfc261-f204-417c-b865-f023bbec3dba" />

The analysis shows strong positive correlations between trip miles, trip time, base passenger fare, and driver pay, meaning that as these factors increase, driver pay tends to rise as well. BCF (Black Car Fund) also has a positive relationship with both driver pay and base passenger fare. On the other hand, some variables show weak negative correlations (e.g., -0.04), but these relationships are negligible and do not significantly affect the analysis.

