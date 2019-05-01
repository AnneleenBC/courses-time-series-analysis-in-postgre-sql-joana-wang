# courses-time-series-analysis-in-postgre-sql-joana-wang

## Step 1) Brainstorming


**What problem(s) will students learn how to solve?**


If students need to work with data that contains dates and/or times.

These are some of the most common problems I've come across while working with dates in industry:

- How long has it been since a client made an order?
- On average, how long does it take for us to ship an order since it was ordered?
- What's the company's revenue in the last 7 days?
- How is revenue performing vs the previous month?
- When was the first time a customer contacted us?
- What are the average monthly orders by customer?
- What is the YTD revenue?
- Which days of the week do stores get most of their footfall in?
- How many days between orders being placed?


This course will teach students how to work with data through time.

- Recognising and preparing data in the correct date formats before applying date operations
- Converting and manipulating data in the different time frames i.e. create data by year, by month, by week etc
- Doing calculations with dates
- Tracking performance through time



**What are the learning objectives of the course?**


- Recognising different types of date variables (date, datetime, interval)
- How to convert them across different units (by year, by month, by week, etc)
- Doing calculations with dates (adding/subtracting dates, operations between dates)
- Extracting information from date aggregations (first/last, recency, frequency)
- Performing calculations through time that take into consideration other time periods (using window functions to compare time periods, i.e. % change, % of)



**What technologies, packages, or functions will students use?**


All the date functions, window functions

- Conversion: TO_DATE, DATE_PART(), DATE_TRUNC()
- Date functions:  Date +/- Interval, AGE(), NOW(), CURRENT_DATE
- Window functions: LAG/LEAD/SUM()/AVG() OVER (PARTITION BY ORDER BY date)



**What terms or jargon will you define?**


- Date - Contains year, month, day
- Time - Contains hour, minute, second
- Datetime/Timestamp - Contains year, month, day, hour, minute, second
- Time part - Any individual component of a date and/or timestamp i.e. year or day or decade etc
- Level of detail - How granular the data is i.e. what is the most detailed piece of information we can get from our data?
- Aggregation - Combined data
- Cumulative - Taking into account all the data from the previous dates



**What analogies or heuristics will you use?**


Might use timelines to explain data occurring at different points in time.
Maybe sometimes make a comparison to the student commuting on a daily basis.



**What mistakes or misconceptions do you expect?**


- Something that students struggle with often (especially coming from a spreadsheets background) is wanting to see dates in a specific manner by trying to format it (but end up using strings).
- Might be a bit of a conceptual jump to go from row-by-row thinking to a moving window approach in window functions.
- Using date parts in a discrete vs continuous manner i.e. "show sales by month" could be just Jan and Feb regardless of year or it could be Jan 2015, Feb 2015, Jan 2016, Feb 2016.
- More of an issue than mistake - Having gaps in data that become very flagrant when working with dates e.g. calculate average daily sales when there is one day of data missing. However, this might be a bit too advanced to show how to get around on this course.



**What datasets will you use?**


I would like to use fitness data from someone's running performance.
Each row would be one run that not only would contain start and stop times, but also duration and speed (time and distance).

If I can't find that, I might use data from a bicycle share scheme that has a similar concept:
https://www.kaggle.com/yingwurenjian/chicago-divvy-bicycle-sharing-data



## Step 2) Who is this course for?

- Unaware Umberto: Someone who is relatively new to programming but has started off with some SQL already and is expanding their SQL knowledge

- Starting Sindhu: Someone who would know already what kind of date operations they would want to do but just missing the syntax to do so



## Step 3) Course Outline


**Chapter 1)	Preparing dates**


This will focus on just preparing data as dates before it can be used for date operations.

Lesson 1.1)	Identify different date formats (date, datetime, epoch, interval etc)
Outcome:	Convert date type variables into different formats
Example:	Turn sale timestamp into sale date in preparation for aggregation to daily sales

Lesson 1.2)	Using strings as dates
Outcome: 	Convert strings to dates
Example:	Take a string that looks like a date and turn into actual date, change date format i.e US to EU 

Lesson 1.3)	Learn how to extract specific parts of dates
Outcome: 	Use DATE_PART in many combinations
Example:	Create new column just for year, month, week number etc


	
**Chapter 2)	Calculations with dates**


Lesson 1.1)	Adding and subtracting dates
Outcome:	Apply date operators
Example:	Add months to date, subtract days to date, using these to filter etc

Lesson 1.2)	Calculating time ranges (intervals)
Outcome:	Calculating difference between two dates using AGE function
Example:	Difference between order date and shipment date, difference between order date and current date

Lesson 1.3)	Extracting specific parts from intervals
Outcome:	Use DATE_PART() on intervals
Example:	How many years have elapsed since graduation date

Lesson 1.4)	Converting intervals to a different unit
Outcome:	Use DATE_TRUNC() and/or EXTRACT()
Example:	Turning 1 year 3 months 15 days interval into number of months and/or rounding to nearest month (1 year 3 months)
	


**Chapter 3)	Date aggregations**


Lesson 1.1)	Identifying first and last dates
Outcome:	Apply MIN and MAX to dates
Example:	Calculate the first and last time a customer purchased something

Lesson 1.2)	Identifying recency
Outcome:	Calculate time since last date
Example:	Calculate how long it's been since the last time a customer purchased something

Lesson 1.3)	Identifying frequency
Outcome:	Set timeframe boundaries and count occurences
Example:	Calculate how many times a customer purchased something between two dates
	

	
**Chapter 4)	Calculations through time**


Lesson 1.1)	Doing calculations through time
Outcome:	Create a window function ordered by date
Example:	Calculate order of purchases with ROW_NUMBER() OVER (PARTITION BY customer ORDER BY order_date)

Lesson 1.2)	Change between time periods
Outcome:	USE LAG and LEAD to calculate differences between rows
Example:	Calculate change of revenue in daily sales

Lesson 1.3)	Change through time periods: Running sum
Outcome:	Create a window function that adds revenue through time
Example:	Calculate cumulative sales YTD

Lesson 1.4)	Change through time periods: Moving average
Outcome:	Create a window function that calculates the average for a set period
Example:	Calculate average daily sales in the last 30 days



