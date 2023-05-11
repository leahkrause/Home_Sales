# Home_Sales

First, I used the CSV to read in the home sales data. I used this data to create a temporary table called home_sales. 

Using Spark SQL, I determined the average price for a four-bedroom house sold grouped by year built. 

Using the same technique, I found the average price of a home for each year built that had three bedrooms and three bathrooms.

Next, I determined the average price of a home for each year built that had three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet. 

Finally, I found the "view" rating of $473,796.26 for homes costing more than or equal to $350,000. This is the average cost of homes that are above the price threshold of $350,000.

In order for the processing to go a bit faster, I cached the home_sales table created, checked that the table was cached, and re-ran the last process. The runtime for this code was approximately 0.2 seconds faster than the previous runtime. 

Next, I partioned the data by "date_built" on the formatted parquet home sales table and created a temporary view for this data. I ran the last process again and determined that this was actually the slowest runtime at approximately 1.6 seconds. 

Finally, I uncached the table and used spark.catalog.isCached to determine that it was uncached.
