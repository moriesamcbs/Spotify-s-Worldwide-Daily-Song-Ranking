

## **Spotify’s 2019 Worldwide Daily Song Rankings** <br>         
#### The 200 daily most streamed songs in 10 countries

___


3#### *Acknowledgment:* This task is inspired by a project done by *http://eduar.do* shared on Kaggle with the context of exploring how artists and song’s popularity varies overtime *here*. This work is an extension of the same by analyzing daily ranking of the 200 most listened songs by Spotify users in 10 countries that contribute most to Spotify’s bottom line *here*.



### Introduction
___

*Spotify* transformed music listening forever when it launched in Sweden in 2008 and became one of the most popular global audio streaming subscription service with 271m users, including 124m subscribers, across 79 markets. All throughout the last year, users have streamed countless hours of their favorite songs, artists, playlists, and podcasts. In this analysis, using Spotify’s chart of 2019 I will highlight the common trends and use a timeseries model to forecast the number of tracks stream and its associated popularity.

#### Data

Dataset contains the daily ranking of the 200 most listened songs in USA, UK, Mexico, Germany, Brazil, Canada, Australia, Netherlands, France and Sweden. It contains 730,000 rows, which comprises 2574 artists, 8825 songs for a total count of eighty-eight billion streams count.
The data spans from 1st January 2019 to 31st December 2019 and includes 7 columns.
It has been collected from Spotify's regional chart data.


### Objective and MVP
___

Data is scrapped by downloading the CSV file using Spotify top 200 daily API and converted to a Pandas data frame.  I later created PostgreSQL Database using Heroku to create a SQL table database and then stored the queried table as a new data frame. Missing data have been removed from the table as they were insignificant and region codes are all replaced with the country’s name. categorical variables are encoded as part of the data processing.



### Data Scrapping, Cleaning & Feature Engineering
___

Data is scrapped by downloading the CSV file using Spotify top 200 daily API and converted to a Pandas data frame.  I later created PostgreSQL Database using Heroku to create a SQL table database and then stored the queried table as a new data frame. Missing data have been removed from the table as they were insignificant and region codes are all replaced with the country’s name. categorical variables are encoded as part of the data processing.


### Data Analysis
___

For easier analysis and collaboration, I have built a dashboard to visualize and track Spotify music trends. For a more in-depth insights, download and interact with this sample dashboard on *Tableau Public.* <br>

![Tableau](http://localhost:8890/view/plots/Tableau_3.png)



### Modeling
___

I will compute VAR time series model and take rank and streams to forecast these variables simultaneously. As fitting process, I will confirm stationary of the data using augmented Dickey-Fuller Test. After splitting data into train/test sets, I will determine correct lag order and after fitting the model I use AIC to select the value of p and generate forecasts.

Summary of Regression Results

The test MSE on the Rank Position data is:
The test MSE on the Streams data is:



### Conclusion and Next Steps
___

In general, the popularity rating is based on total number of streams compared to other tracks as well as how recent those streams are, however that alone does not factor in determining the songs success. As shown in the data, countries share the same top-ranking songs, and that shows how factors like social trend, location, artist and genre are significant to track’s popularity. Nonetheless, exploring songs features could provide further insights for artists and music agents who are looking for Spotify users view and their perceived values.

Next steps identified to expand on this project are as follows:<br>
-Real Time KPI Dashboard:  connecting to Spotify data and get the latest data from Spotify’s charts and bring it into Tableau for analysis.<br>
- Extend the data set to include all countries where Spotify is available and add podcast as a separate category.<br>
- Further analysis to learn engagement by streaming device e.g. phone, computer or tablet.<br>
- Explore impact of attributes such as song genre, keys, energy, danceability, instrumentals, etc. on its popularity and create a regression model to predict song’s popularity based on these features.



### Sources & Requirements
___

• Spotify | Charts: (https://spotifycharts.com/regional)
• Scikitlearn==0.21
• Spotipy== fycharts.SpotifyCharts Tweet
• Pandas==1.0.
