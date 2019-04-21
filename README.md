
## Step 1-Climate Analysis and Exploration

To begin, use Python and SQLAlchemy to do basic climate analysis and data exploration of your climate database. All of the following analysis should be completed using SQLAlchemy ORM queries, Pandas, and Matplotlib.

* Used SQLAlchemy `create_engine` to connect to your sqlite database.

* Used SQLAlchemy `automap_base()` to reflect your tables into classes and saved a reference to those classes called `Station` and `Measurement`.

### Precipitation Analysis

* Designed a query to retrieve the last 12 months of precipitation data.

* Selected only the `date` and `prcp` values.

* Loaded the query results into a Pandas DataFrame and set the index to the date column.

* Sorted the DataFrame values by `date`.

* Ploted the results using the DataFrame `plot` method.

* Used Pandas to print the summary statistics for the precipitation data.

### Station Analysis

* Designed a query to calculate the total number of stations.

* Designed a query to find the most active stations.

  * Listed the stations and observation counts in descending order.

  * showed which station has the highest number of observations.

  * used functions such as `func.min`, `func.max`, `func.avg`, and `func.count` in queries.

* Designed a query to retrieve the last 12 months of temperature observation data (tobs).

  * Filtered by the station with the highest number of observations.

  * Ploted the results as a histogram with `bins=12`.

    
### Temperature Analysis (Optional)

* calculated the min, avg, and max temperatures for your trip using the matching dates from the previous year (i.e., use "2017-01-01" if your trip start date was "2018-01-01").

* Ploted the min, avg, and max temperature from your previous query as a bar chart.

  * Useed the average temperature as the bar height.

  * Used the peak-to-peak (tmax-tmin) value as the y error bar (yerr).

 - - -

## Step 2 - Climate App

designd a Flask API based on the queries developed.

* Used FLASK to create routes.

### Routes

* `/`

  * Home page.

  
* `/api/v1.0/precipitation`

  * Converted the query results to a Dictionary using `date` as the key and `prcp` as the value.

  * Returned the JSON representation of your dictionary.

* `/api/v1.0/stations`

  * Returned a JSON list of stations from the dataset.

* `/api/v1.0/tobs`
  * queryed for the dates and temperature observations from a year from the last data point.
  * Returned a JSON list of Temperature Observations (tobs) for the previous year.

* `/api/v1.0/<start>` and `/api/v1.0/<start>/<end>`

  * Returned a JSON list of the minimum temperature, the average temperature, and the max temperature for a given start or start-end range.

  * When given the start only, calculated `TMIN`, `TAVG`, and `TMAX` for all dates greater than and equal to the start date.

  * When given the start and the end date, calculated the `TMIN`, `TAVG`, and `TMAX` for dates between the start and end date inclusive.

