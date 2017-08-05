# Diablo Velo
[Strava](http://strava.com) has become an extremely popular activity-tracking app for cyclists. As such, it offers a trove of cycling data for analyzing. In this project, I analyze and predict the amount of time it would take a given cyclist to ride from the north entrance gate to the summit of Mount Diablo, which is an iconic mountain-climbing route in the San Francisco Bay Area's cycling community. See the Strava segemnt [here](https://www.strava.com/segments/656860). 

The code in this repo obtains all cycling efforts on the Diablo Northgate-to-Summit segment from [Strava's API](https://strava.github.io/api/), scrapes weather data from [Weather Underground's weather history page](https://www.wunderground.com/history/airport/KCCR/2006/1/1/DailyHistory.html?req_city=Walnut+Creek&req_state=CA&req_statename=California&reqdb.zip=94595&reqdb.magic=1&reqdb.wmo=99999) for the days corresponding to each cycling effort, combines and cleans the data, graphically explores the data, and trains a least-squares regression model to predict riders' moving times based on performance- and weather-related features.

## Requirements
* Install the required libraries by running `pip install -r requirements.txt` from the repo directory
* A Strava API access token is required to access Strava's API (see authentication details [here](https://strava.github.io/api/v3/oauth/)). 
* Create a file called `strava_api.py` in the repo directory. Within that file populate a string variable `access_token` with your own access token.
* Note that all code was written in Python 3

## Usage
1. Run `get_diablo_data.ipynb` to retrieve the data from Strava and Weather Underground
2. Run `clean_diablo_data.ipynb` to convert the Strava Data from JSON format to a pandas dataframe, join the cleaned Strava data with the Weather Undergound data, transform and generate some features, and export the joined, cleaned data to a CSV file
3. Run `explore_and_model_diablo_data.ipynb` to generate exploratory graphics and train a regression model on the data
