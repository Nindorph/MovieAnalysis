Microsoft Studios Movie Analysis

Authors: Danielle Rossman, Nick Indorf, Jeff Marvel

Summary: 

This project analyzes movie data from the last ten years (2010-2019) to determine what characteristics have driven box office success as measured by Return on Investment (ROI). The project culminated in three business recommendations for the hypothetical launch of a new movie studio.


Data and sources:

* IMDB: data on movie names, staff (director, actor, etc), and grenre from the past 10 years.
* The Numbers: data on profitability (worlwide gross, production budget) for each movie
* MovieTweeting: repository of "well-structured" tweets that contain a movie review (https://github.com/sidooms/MovieTweetings/blob/master/README.md) 


Navigating the repository: 

The original datasets for IMDB and The Numbers can be found in the "Zipped Data" folder.
Data on MovieTweeting are contained in movies.dat and ratings.dat
data_cleaning_final.jpynb: notebook that consolidates datasets and performs other cleaning steps. Outputs a clean CSV file that is used in the final analysis.
movie_analysis_final.jpynb: notebook that performs analysis that underlines each recommendation. Leverages final CSVs produced by the Data Cleaning notebook. Includes a for each of the recommendations and prints / saves the final graphs used in the presentation.
Graphs used in final presentation are found in the "images" folder.


Further detail on approach and methodlogy:

Datasets were merged based on a concatenation of year and movie title (to prevent movies with the same name being included twice). Further data cleaning steps were taken, including: 
  
* Removing a handful of Null values
* Removing outliers
* Filter only for movies with at least a $100K production budget (rationale is that Microsoft isn't likely to produce such a low budget movie)
* For the analysis of twitter reviews, I removed movies that received under 50 reviews (to prevent skew in the results)


Recommendation #1: Horror / Thriller movies tend to perform significantly better than average at the box office.

Details: Grouping the dataset by genre and sorting by average ROI, Horror, Mystery, and Thriller movies stand out from the pack in terms of ROI. These movies have an ROI that is 108% higher than average. This is not necessarily surprising since Horror movies, while they may not win any oscars, consistently draw large crowds and perform well. The below graph illustrates this relationship.

! <show path to the graph>

Recommendation #2: Target a "to-hire" list of directors / actors and other movie employees that consistently outperform the mean.
  
Our analysis found a subset of people that consistently produce box office success.See graphs below.
  

Recommendation #3: Focus on making good movies and invest in social media presence.
  
Details: Our dataset included two sources of reviews. 1. Reviews on IMDB.com and 2. Reviews from "well-structured" tweets on Twitter. 
  
The first step of the analysis was to determine if there is a relationship between review quality and profitability. Our analysis suggests that there is. For movies with "good" reviews (defined as 8+ on IMDB), ROI is 68% higher than average. This was particularly true for Horror / Thriller movies, which had 100% higher ROI than average. The reason for using 8 as the cutoff for "good" is that the population average is around ~7. People don't appear to leave bad reviews. This result suggest that there is real value, particularly for Horror movies, in clearing the bar of a 8 or higher review.
  
The second step of the analysis was to determine if social media engagement drove higher ROI. The hypothesis is that total number of tweets, as a rough proxy for "social media" buzz, would lead to higher ROI. The data bears this hypothesis out. Movies with high twitter engagement (defined as 500+ well-structured tweets), materially outperformed average ROI. This is particularly true when you look at more recent data. For movies made since 2017, high engagement on Twitter suggest an ROI that is 115% higher than average. The punchline is that as social media becomes more and more embedded in our lives, this relationship only becomes more important.
  
  
Conclusion:
* Horror, Mystery, and Thriller movies pay
* There is a subset of movie talent that consistently produce high ROI movies
* Good reviews and social media engagement matter for the eventual box office success of a new movie

  
Further analysis:
* 
