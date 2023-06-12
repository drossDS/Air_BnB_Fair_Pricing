# Project : Boston Airbnb Fair Pricing Tool and Recommender
## Daniel Rossetti, Founder, Data Scientist for 'Cheap Stays, LLC'

# 1. Problem Statement
This report is written from the standpoint of an entrepreneur (Data Scientist and founder of Cheap Stays, LLC) looking to create a digital product which will help users quickly identify the fair price for an Airbnb which matches their desired criteria. It will also recommend Airbnb listings which match their criteria.

Airbnb is a popular website for those who travel for business or pleasure and need lodging but choose not to go the traditional hotel-route.  Usually, hosts offer-up their personal or secondary properties for people to stay at for a fee.  This fee may be cheaper than hotels while also providing the comforts of a furnished home depending on the type of listing.  Some individuals (hosts) will offer their dwellings as a source of passive income, and others have made Airbnb their main income stream.  Potential guests would likely find it beneficial to understand what constitutes a 'fair' price for an Airbnb given a set of desired criteria.  They would further be interested in seeing listings matching their input criteria at the same time.  Potential hosts may be looking to understand the current market for Airbnb listings similar to their own and would benefit from a pricing tool and similar listing recommender.

This project will seek to determine if an accurate fair-pricing tool can be developed to predict the prices of Airbnb listings in the Boston area while providing suggestions for currently listed Airbnb’s.  The accuracy of the pricing tool will be evaluated by the root mean squared error, and the target error will be approximately equal to $20 given that most Airbnb listings are listed in the low hundreds of dollars.

# 2. Project Approach and EDA
## 2.1.  Code Notebooks (Notebook Directory)
There are six notebooks associated with this project.  A quick overview of each will be provided here:

* Notebook 1 - Exploratory Data Analysis.  Creates train, test, validation datasets, and performs simple EDA on numerical and categorical variables.  This excludes EDA on columns which require advanced preprocessing and feature engineering
* Notebook 2 - Feature Engineering Part 1.  Examines the features excluded from EDA and extracts or creates new features
* Notebook 3 - Feature Engineering Part 2.  Creates a feature loosely representing the distance from each listing to the nearest public transit (subway) stop obtaining additional data from the web
* Notebook 4 - Data Preprocessor and Compiler - Creates functions which perform all necessary transformation steps (previously performed in Notebooks 1, 2 and 3) to all datasets
* Notebook 5 - Modeling - Selects features based on correlation and creates price prediction models
* Notebook 6 - Recommender - Creates a near-prototype fair price and listing recommender tool


# 3. Description of Data
## 3.1. Notebook 1 - Airbnb Data
* "Inside Airbnb" is a database which regularly collects Airbnb listing data for multiple cities around the world.  The website can be accessed [here](http://insideairbnb.com/get-the-data/) by scrolling down to where Boston is listed
* The actual data was downloaded in the Boston section by clicking the '[listings.csv.gz](http://data.insideairbnb.com/united-states/ma/boston/2023-03-19/data/listings.csv.gz)' link
* The data dictionary can be accessed from the main webpage above and is located [here](https://docs.google.com/spreadsheets/d/1iWCNJcSutYqpULSQHlNyGInUvHg2BoUGoNRIGa6Szc4/edit#gid=1322284596)

The data were downloaded on 2023-05-30 and are from the most recent scraping dated 2023-03-19 on the Inside Airbnb website


Other data are sourced in Notebook 3 from the Massachusetts Bay Transit Authority (MBTA) Website and the Google Geocoding API.  Those sources will be discussed in greater detail in that notebook.

## 3.2 Notebook 2 - Suplemental Data
Supplemental data are gathered in an attempt to create features mimicing the distance between a listing's location and the closest subway stop.  Latitude and longitude data are provided for each listing from Inside Airbnb, and the subway stop locations were gathered via the following method:
* The [MBTA Stations](https://www.mbta.com/stops/subway) page was scraped to find all urls for all stations
* Station site was then scraped to find the station address
* The Google Geocoding API was then used to retrieve latitude and longitude for each address.  See the documentation [here](https://developers.google.com/maps/documentation/geocoding)

# 4. Modeling

## 4.1. Modeling Evaluation Metrics
The root mean squared error is the primary model evaluation metric as it would be expressed in the same units as the target variable, price.  This is a very tangible measure of how variable a model is simply because it outputs dollar amounts.

The R-squared value will act as a secondary metric to quickly evaluate the quality of the model itself and how much better (if at all, it is compared to the null model).

# Discussion/ Summary

# Conclusions
## Fair Pricing Model Conclusions

## Recommender Conclusions