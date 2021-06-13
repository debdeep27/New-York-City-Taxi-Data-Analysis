# New-York-City-Taxi-Data-Analysis
Data Analysis of New York City Taxi Data for October 2013

### Data Cleaning & Preprocessing
- Working with data for the month of October 2013
- More than 15M records
- More than 7M null values for store_and_fwd_flag and 736 null values for dropoff longitude and latitude
- Removed records where dropoff longitude and latitude was null
- Dropped store_and_fwd_flag column, it was not useful for the analysis
- Removed records where the pickup and dropoff coordinates were beyond a certain boundary, i.e., limiting records within New York City
- Removed records where trip_distance is less than geodesic distance and where it is 0
- Created a new column with the calculated trip time in seconds, ignoring the meter generated trip_time_in_secs. Also only kept rows where the new value is greater than 0
- Limited records within Average Speed of 65 miles/hr
- Removed rows where passenger count was either 0, 7 or 9
- Kept rows where Rate Code was within 1 to 6
- Merged the fare data to the trip data

### Feature Engineering
- Using Z-Score removed rows where the fare amount exceeded 4th standard deviation
- Removed unnecessary columns like 'medallion', 'hack_license', 'pickup_datetime', 'dropoff_datetime', 'trip_time_in_secs', 'trip_dist_miles’
- Scaled numerical columns using MinMaxScalar()
- Converted 'vendor_id', 'rate_code', 'passenger_count', 'payment_type', 'pickup_weekday', 'pickup_hour', 'pickup_day' into dummy variables
- Split the dataset into predictor and target features
- Split the dataset into Training (70%) and Testing (30%)

### Note:
If you want to run the code. Please follow the below steps:
- There are 6 ipynb files (ignore files that have 'version' in them)
- Run ny_taxi_data_cleaning.ipynb first and generate the cleaned data, which has been used for all other notebooks. (Also change the paths where you have downloaded and stored the data)
- Analysis is done in : ny_taxi_data_analysis.ipynb
- Fare Amount Modelling and Prediction done in: ny_taxi_data_predict_trip_fare.ipynb, ny_taxi_data_predict_trip_fare_neural_network.ipynb
- Tip Amount Modelling and Prediction done in: ny_taxi_data_predict_trip_tip_amount.ipynb, ny_taxi_data_predict_trip_tip_prediction_neural_network.ipynb
- One last thing please also import any other packages that you may not have installed.
