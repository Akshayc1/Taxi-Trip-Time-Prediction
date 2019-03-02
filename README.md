# Taxi-Trip-Time-Prediction
Link for Dataset : https://www.kaggle.com/crailtap/taxi-trajectory

Data Overview

Each data point corresponds to one complete trip. It contains a total 9 features

* TRIP_ID (string) : It contains an unique identifier for each trip
* CALL_TYPE (char) :  It identifies the way used to demand this service. It may contain one of three possible values.
                      1. 'A' : if this trip was dispatched from the central
                      2. 'B' : if this trip was demanded directly to a taxi driver on a specific stand
                      3. 'C' : otherwise (i.e. a trip demanded on a random street)
* ORIGIN_CALL (integer) :  It contains an unique identifier for each phone number which was used to demand, at least, one service. It identifies the trip’s customer if CALL_TYPE=’A’. Otherwise, it assumes a NULL value
* ORIGIN_STAND (integer): It contains an unique identifier for the taxi stand. It identifies the starting point of the trip if CALL_TYPE=’B’. Otherwise, it assumes a NULL value
* TAXI_ID: (integer): It contains an unique identifier for the taxi driver that performed each trip
* TIMESTAMP (integer) : Unix Timestamp (in seconds). It identifies the trip’s start
* DAYTYPE (char) : It identifies the daytype of the trip’s start. It assumes one of three possible values
                    1. 'B' : if this trip started on a holiday or any other special day (i.e. extending holidays, floating holidays, etc.)
                    2. 'C' : if the trip started on a day before a type-B day
                    3. 'A' : otherwise (i.e. a normal day, workday or weekend)
* MISSING_DATA (Boolean) : It is FALSE when the GPS data stream is complete and TRUE whenever one (or more) locations are missing.
* POLYLINE (String): It contains a list of GPS coordinates (i.e. WGS84 format) mapped as a string.The last list item corresponds to the trip’s destination while the first one represents its start. The beginning and the end of the string are identified with brackets (i.e. [ and ], respectively). Each pair of coordinates is also identified by the same brackets as [LONGITUDE, LATITUDE]. This list contains one pair of coordinates for each 15 seconds of trip. The POLYLINE can have multiple pairs of longitude and latitude


The total travel time of the trip (the prediction target) is defined as the (number of points-1) x 15 seconds. For example, a trip with 101 data points in POLYLINE has a length of (101-1) * 15 = 1500 seconds. 



Type of Machine Learning task : 
It is an regression problem where given a set of features we need to predict the total travel time by taxi from starting of ride to the destination in seconds.
                    
                
