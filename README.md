# DSA210-Term-Project

This project aims to analyze how seasonal trends and visibility/interaction on social media affect movies' popularity and box office value. Along with the relationship seasonal increase/decrease in certain genres (spike in popularity for holiday movies during the period between Christmas - New Years), there will also be comparison between the effects of social media engagement vs critics' rating & recommendation on how high the revenue of the movie is. 

## Motivation
With the increased digitalization of the world, online streaming platforms have become a major source for streaming movies and series and are considered to have replaced the physical streaming (cinemas/box office) industry. Digitalization has also contributed to social media spaces majorly being the host platforms for discussions and generating engagament for visual media like movies and series. Since movies' and their online discussion spaces are personal interests of mine, I intend to question some of the major factors affecting movies' popularity and plan to focus on the global annual calendar/major events along with online engagement on search engines and content based social media platforms.

## **Research Questions:** 
Aiming to answer questions like:
- Does generating social media engagement have a bigger impact on box office revenue and streaming watch counts compared to being critically acclaimed (e.g: on platforms like Rotten Tomatoes and TMDb)?
- To what extent do seasonal trends and annual events (Halloween, Christmas, summer and winter breaks for students) affect the popularity of certain genres of movies?
- To what extent does increased engagement on social media and popularity on search enginges correlate with a movie's box office revenue and view count on streaming platforms after it is released?

## **Hypotheses:**
- **Null Hypothesis (H₀):** Engagement on social media and search engines, seasonal trends, and critic/audience ratings do not have a significant impact on a movie's popularity and revenue.
- **Hypothesis 1 (H1):** Engagement on social media and search engines, seasonal trends, and critic/audience ratings are all factors that significantly impact a movie's popularity and revenue.

## Datasets
- movie-title
- genre: genre of the movie
- tmdb-popularity: a movie’s popularity score that is based on user ratings, searches and overall interaction
- tmdb-revenue: revenue of a movie in dollars
- peak-interest: highest interest for a movie on Google (search engine)
- avg-interest: average interest for a movie on Google over time (0-100)
- date: date belonging to the data avg-interest and peak-interest retrieved on Google Trends (YYYY-MM-DD)
- critic-score: the average score (0-100) given to the movie by critics
- audience-score: the average score (0-100) that represents how the movie is perceived by the general public 

The mentioned features will be collected from the following sources:
- TMDb (The Movie Database): retrieved via TMDb API Key for Non Commercial Use and installment of the wrapper [tmdbsimple](https://github.com/celiao/tmdbsimple.git) by celiao for Python
  - tmdb-popularity abd tmdb-revenue will be retrieved from TMDb
- Google Trends: to track Google searches about trending movies at certain times: search data over time will be retrieved via Pytrends using pytrends library on Python and stored on pandas
  - peak-interest and avg-interest will be retrieved from Google Trends
- Rotten Tomatoes: Installment of the library [rottentomatoes](https://github.com/preritdas/rottentomatoes-python.git) for Python by preritdas to access both critic rating and audience scores
  - genre, critic-score, audience-score will be retrieved from Rotten Tomatoes
 
Additionally, sentiment analysis using an IMDb reviews dataset retrieved on Kaggle (including user-reviews and sentiment-value features) is to be implemented. Such data will contribute to showing how reviews and their sentiment value correlate with the other features included in the project (Rotten Tomatoes scores by critics and the audience, TMDb popularity score, interest on Google etc.) 

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
