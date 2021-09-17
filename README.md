Microsoft Studios Movie Analysis

Authors: Danielle Rossman, Nick Indorf, Jeff Marvel

Summary: 

This project analyzes movie data from the last ten years (2010-2019) to determine what characteristics have driven box office success as measured by Return on Investment percentage (ROI%). The project culminated in three business recommendations for the  launch of Microsoft's new movie studio, presented [here](https://docs.google.com/presentation/d/1klWg1TuGNnFnyVte3Z8LerU-2E2BE98NHsQzit1o35c/edit?usp=sharing)


Data and sources:

[IMDB datasets](https://www.imdb.com/interfaces/): multiple datasets on general movie info, genre, ratings, and staff (director, actor, etc) from the past 10 years.
[The Numbers](https://www.the-numbers.com/data-services): data on profitability (worlwide gross, production budget) for each movie
[MovieTweeting](https://github.com/sidooms/MovieTweetings/blob/master/README.md): repository of "well-structured" tweets that contain a movie review  


Navigating the repository: 

In the main directory:

`data_cleaning_final.jpynb`: notebook that consolidates datasets and performs other cleaning steps. Outputs a clean CSV file that is used in the final analysis.
`Movie_analysis_final.jpynb`: notebook that performs analysis that underlines each recommendation. Leverages final CSVs produced by the Data Cleaning notebook. Provides a rationale for each of the recommendations and prints / saves the final graphs used in the presentation.

In the `zippedData` directory:

The original datasets for IMDB:
* `imdb.title.basics.csv.gz`
* `imdb.title.ratings.csv.gz`
* `imdb.title.principals.csv.gz`
* `imdb.title.crew.csv.gz`
* `imdb.title.basics.csv.gz`
* `imdb.name.basics.csv.gz`

The original datasets for The Numbers:
* `tn.movie_budgets.csv.gz`

The original datasets for MovieTweeting
* `movies.dat`
* `ratings.dat`


In the `images` directory:
Figures used in final presentation


Approach and methodology:

IMDB sub-datasets were first merged together to create a large composite IMDB dataset.
The Numbers dataset was processed to adjust profit and cost for inflation, as well as ROI%
The IMDB composite and The Numbers were merged based on a concatenation of year and movie title (to prevent movies with the same name being included twice).

Further data cleaning steps were taken, including:   
* Removing a handful of Null values
* Removing outliers
    - ROI% > 6000 (2 movies) - skewed dataset too highly
    - Worldwide Gross < $100K (52 movies) - potentially just a limited run with low scope - not relevant to Microsoft's interests
* For the analysis of twitter reviews, removed movies that received under 50 reviews (to prevent skew in the results)

This yielded a composite dataset for downstream analysis. A histogram of ROI distributions is provided.


Recommendation #1: Horror / Thriller movies tend to perform significantly better than average at the box office.

Grouped the dataset by genre and sorting by average ROI.

Horror, Mystery, and Thriller movies stand out from the pack in terms of ROI. These movies have an ROI that is 108% higher than average. This is not necessarily surprising since Horror movies, while they may not win any oscars, consistently draw large crowds and perform well. The below graph illustrates this relationship.



Recommendation #2: Target 6 "to-hire" movie cast/crew who consistently outperform their peers.
  
Grouped the dataset by person in each role (meaning job in the cast/crew), then sorted to find the top performers.
This subset was filtered for people who have worked on at least 2 and at least 3 movies (to make sure 
  

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
