# Restaurant Violations ETL Project

## Team Effort
Nick Majeski, Sineekarn (Aom) Watcharawikran, Anne Marie Sticksel

## Project Proposal

We would like to compare information about restaurant violations in the city of Chicago with the rating, reviews, and pricing for popular restaurants to see if there is any correlation between restaurants with lots of violations and how well they are rated.

## Extract
Our data sources are:
* Chicago City Data
https://data.cityofchicago.org/Health-Human-Services/Food-Inspections/4ijn-s7e5
(formatted originally as a CSV)

* Yelp Data
https://www.yelp.com/developers/documentation/v3/business_search
(pulled Yelp API with Postman, output as JSON)




## Transform
* Created a dataframe for Chicago data, and a dataframe for Yelp data by combining individual JSON files from API calls

* We cleaned address names to be in all caps, and restaurant names to have as consistent naming conventions between data sources (all caps, AND instead of &, spaces instead of dashes)
* Removed uncessary columns
* Separated dictionary data from JSON file into individual columns
* Rename columns


* Joining Data: We joined the data on Restaurant Name and Address. Latitude and Longitude data wasn't the same between the two databases, so we could not use it.

* Extracted relevant columns from the joined data into a final dataframe, created consistent column names and naming conventions (column names are all lower case, spaces in column names are underscores)

## Load
* Created a table in postgres
* Connected to SQL engine
* Loaded joined dataframe into postgres
