# DSA210-Term-Project

This project aims to analyze how seasonal trends and visibility/interaction on social media affect movies' popularity and box office value. Along with the relationship seasonal increase/decrease in certain genres (spike in popularity for holiday movies during the period between Christmas - New Years), there will also be comparison between the effects of social media engagement vs critics' rating & recommendation on how high the revenue of the movie is. 


## Motivation
With the increased digitalization of the world, online streaming platforms have become a major source for streaming movies and series and are considered to have replaced the physical streaming (cinemas/box office) industry. Digitalization has also contributed to social media spaces majorly being the host platforms for discussions and generating engagament for visual media like movies and series. Since movies' and their online discussion spaces are personal interests of mine, I intend to question some of the major factors affecting movies' popularity and plan to focus on the global annual calendar/major events along with online engagement on search engines and content based social media platforms.

## **Research Questions:** 
Aiming to answer questions like:
- Does generating social media engagement have a bigger impact on box office revenue and streaming watch counts compared to being critically acclaimed (e.g: on platforms like Rotten Tomatoes and IMDb)?
- To what extent do seasonal trends and annual events (Halloween, Christmas, summer and winter breaks for students) affect the popularity of certain genres of movies?
- To what extent does increased engagement on social media and popularity on search enginges correlate with a movie's box office revenue and view count on streaming platforms after it is released?

## **Hypotheses:**
- **Null Hypothesis (H₀):** Engagement on social media and search engines, seasonal trends, and critic/audience ratings do not have a significant impact on a movie's popularity and revenue.
- **Hypothesis 1 (H1):** Engagement on social media and search engines, seasonal trends, and critic/audience ratings are all factors that significantly impact a movie's popularity and revenue.

## Datasets
Data will be collected using the following sources:
- Google Trends: to track Google searches about trending movies at certain times
  - search data over time will be retrieved via Pytrends using pytrends library on Python and stored on pandas
- Reddit: to observe social media engagement and discussions around certain movies and how they changed over time on subreddits r/movies, r/Letterboxd, r/TrueFilm.
  - Reddit Pushshift Archives: to collect bulk historical data
  - PRAW API: PRAW (Reddit official API) library on Python for recent engagement data on certain subreddits and including certain keywords
- TMDb (The Movie Database): data of trending movies, genres and dates over certain time periods
  - retrieved via TMDb API Key for Non Commercial Use and installment of the wrapper [tmdbsimple](https://github.com/celiao/tmdbsimple.git) by celiao for Python 
- Rotten Tomatoes: data of critic scores vs. how the movie is perceived bt the general public
  - Installment of the library [rottentomatoes](https://github.com/preritdas/rottentomatoes-python.git) for Python by preritdas to access both critic rating and audience scores
- IMDb: general information about the movies, rating, release dates and box office performance
  - IMDb Non Commercial Datasets will be downloaded from the official IMDb Developer website: including data of ratings and general information (genre, release date..) about the movies

## Data Analysis
- Tracking popularity of movie trends over time.
- Determining seasonal trends.
- Comparing discussions on social media with the success of the movie.
- Identifying correlations between social media engagement and movie popularity, seasonal trends and movie popularity, critic reviews and movie popularity.
- Applying regression analysis to predict success of movie in box office and streaming platforms.

## Findings
This section is to be updated as the project is continuing and results are produced.

## Key Insights, Limitations and Future Work
This section is to be updated later depending on the findings of the project.
