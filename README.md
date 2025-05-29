# DSA210-Term-Project

This project aims to analyze how seasonal trends and critic/audience opinions affect movies' popularity and box office value. Along with the relationship seasonal increase/decrease in certain genres (as an example: spike in popularity for holiday movies during the period between Christmas - New Years), there will also be comparison between the relation between general audience rating vs critics' rating and how high the revenue of the movie is. 

- [Motivation](#Motivation)
- [Research Questions](#Research-Questions)
- [Hypotheses](#Hypotheses)
- [Datasets](#Datasets)
- [Project Roadmap](#Project-Roadmap)
- [Results](#Results)
- [Machine Learning](#Machine-Learning)
- [Limitations & Future Work](#Limitations-challenges-future-work)

## Motivation
With the increased digitalization of the world, online streaming platforms have become a major source for streaming movies and series and are considered to have replaced the physical streaming (cinemas/box office) industry. Digitalization has also contributed to social media spaces majorly being the host platforms for discussions and generating engagament for visual media like movies and series. Since movies' and their online discussion spaces are personal interests of mine, I intend to question some of the major factors affecting movies' popularity and plan to focus on the global annual calendar/major events along with online engagement on search engines.

## Research Questions:
Aiming to answer questions like:
- To what extent do seasonal trends and annual events (Halloween, Christmas, summer and winter breaks for students) affect the popularity of certain genres of movies based on search engine data?
- To what extent do critic ratings and general public opinion (rating) correlate with a movie's box office revenue? Which rating is more indicative of box office success?

## Hypotheses:
### Critic score (tomatoMeter) & box office revenue:
H0: There is no significant relationship between critic score and box office revenue.

Ha: There is a significant relationship between critic score and box office revenue.

### Audience score & box office revenue:
H0: There is no significant relationship between audience score and box office revenue.

Ha: There is a significant relationship between audience score and box office revenue.

### Seasonal trends:
H0: There is no significant difference in popularity of genres across seasons.

Ha: There is a significant difference in popularity of genres across seasons.

### Monthly trends:
H0: There is no significant difference in popularity of genres across months.

Ha: There is a significant difference in popularity of genres across months.

## Datasets
The project will feature the following data:
* title: title of movie
* genre: genre of movie
* interest_over_time: interest for a movie genre over time on Google (search engine)
* date: date belonging to the interest trend retrieved on Google Trends (YYYY-MM-DD)
* tomatoMeter: the average score (0-100) given to the movie by critics
* audienceScore: the average score (0-100) that represents how the movie is perceived by the general public
* boxOffice: box office revenue (in dollars) 

The mentioned features will be collected from the following sources:
* Google Trends: to track Google searches about trending movies at certain times: search data over time will be retrieved via Pytrends using [pytrends](https://pypi.org/project/pytrends/) library on Python and stored on pandas
    * interest data trend of certain genres over time will be collected to examine how the popularity of different genres change depending on the season of the year (genres will be imported from the Rotten Tomatoes dataset) 
* Rotten Tomatoes: usage of a [Rotten Tomatoes Movies dataset](https://www.kaggle.com/datasets/andrezaza/clapper-massive-rotten-tomatoes-movies-and-reviews?resource=download&select=rotten_tomatoes_movies.csv) imported from Kaggle user Andrea Villa to access title, genre, critic scores (tomatoMeter), audience scores and box office revenue data
    * genre, box office, critic score (tomatoMeter), audience score will be retrieved from Rotten Tomatoes

### Data Analysis
- Tracking popularity of movie trends over time.
- Determining seasonal trends.
- Comparing discussions on social media with the success of the movie.
- Identifying correlations between social media engagement and movie popularity, seasonal trends and movie popularity, critic reviews and movie popularity.
- Applying regression analysis to predict success of movie in box office and streaming platforms.

## Project Roadmap
### 1. Data Collection
- Kaggle dataset of Rotten Tomatoes movies (their genres, critic & audience scores, box office revenues)
- Google Trends data of interest per movie genre over the year 2024
### 2. Dataset Cleaning & Organization
Removed rows with missing data, merging and transformation of data as needed
### 3. Exploratory Data Analysis
- Correlation heatmaps
- Seasonal grouping (from months to seasons)
- Time plots, distribution plot
### 4. Hypothesis Testing
- ANOVA for seasonal/monthly genre trend analysis
- Pearson Correlation for box office over critic & audience scores
### 5. Visualization
- Scatterplot of distribution of box office over score & regression line
- Time plot of monthly interest of genres significantly influenced by seasonal trends or annual events
### 6. Machine Learning
- Feature engineering to create and transform features
- Random Forest Classification (classifying box office revenue as low vs high)
- Random Forest Regression (predicting box office revenue)
- Accuracy analysis of models + conclusion
### 7. Results
Findings of:
- Score vs Box Office Revenue
- Seasonal & Monthly Genre Trends
### 8. Limitations & Challenges, Future Work

# Results

## Critic & Audience Scores’ Relation with Box Office Revenue:

In order to understand if a movie’s ratings correlate with how high their box office revenue (in dollars) is, two scores -one being the average of multiple critics and the other one that represents the general audiences’ opinion- on the movie were compared to see if either show any relation. A dataset containing values of over 130 thousand movies, their scores, genres, box office revenue values (and more) scrapped by user Andrea Milla from the website Rotten Tomatoes was retrieved from Kaggle and used in the experiment. The correlation values of both scores were compared with a heatmap to examine if there is indeed any relation. The hypotheses of the experiment were tested using Pearson Correlation. The scatterplots of both comparisons were saved as png files, along with the correlation heatmap of the three data features and can be found in the results folder.

### Results: 
P-value was found to be:
- For audience score & box office revenue: 1.248400337443627e-20
- For critic score & box office revenue: 5.145165271420907e-144

Comparing these values with α = 0.05: we can reject the null hypothesis for both the audience score-box office revenue test and the critic score-box office test. There is a statistically significant relationship between audience rating and box office revenue and between critic scores and box office revenue.

![heatmap_correlation_boxoffice](https://github.com/user-attachments/assets/90d98dbf-f2b6-4cf2-b4cb-5b1c37634140)

Pearson correlation was found to be:
- Between audience score & box office revenue: -0.0901669691353097
    - which means there is a very weak negative correlation between the two values.
- Between critic score & box office revenue: -0.24415258620083363
    - which means there is a weak negative correlation between the two values.

Additionally, on the correlation heatmap, we can observe the pearson correlation between audience score and critic score to be 0.58: which indicates a strong positive correlation between the two values. 

### Visualization:
#### Audience score:
![image](https://github.com/user-attachments/assets/81bb6817-ffa7-4f02-ac3d-8c4fe50683d0)
The relationship between audience rating and box office revenue values is statistically significant according to the result of Pearson Correlation test. However, as seen in the regression plot above, the plot values are scattered in all areas of the graph and the correlation they seem to result in is a very weak (and negative) one.

#### Critic score:
![image](https://github.com/user-attachments/assets/5ee037f2-cceb-47a6-a672-3f44b5518c37)
The relationship between critic rating and box office revenue values is also statistically significant according to the result of Pearson Correlation test. Similarly to the audience rating - box office graph, the plot values seem to be even more scattered in all areas of the graph, and it's hard to see a clear trend. This result suggests critic score is not among the significant factors in predicting a movie'S box office success.

## Seasonal Genre Popularity Trends: 

In order to understand the relationship between seasonal-annual events/days and movie genre popularity, Google Trends’ search popularity data of genres was retrieved using the Python library pytrends. A dataset containing values of over 130 thousand movies, their scores, genres, box office revenue values (and more) scrapped by user Andrea Milla from the website Rotten Tomatoes was retrieved from Kaggle and used in the experiment. The correlation values of both scores were compared with a heatmap to examine if there is indeed any relation. The hypotheses of the experiment were tested using ANOVA. 

### Results:
For every genre that we retrieved data for, winter was the season with most searches- its count being 14 while the other seasons' counts were 13. There was no difference between genres' popularity when grouped according to seasons. On the other hand, popularity of genres differed when evaluated between different months. 

#### Seasonal:
H0: There is no significant difference in popularity of genres across seasons.

Ha: There is a significant difference in popularity of genres across seasons.

- We reject the null hypothesis for the following genres: Adventure, Romance, Standup, Variety, Horror, Biography, Documentary, Mystery & Thriller, Action, Comedy, Fantasy, History, LGBTQ+, Musical, Western, Sci-Fi, Animation, Holiday, War, Music, Sports, Entertainment, News, Nature, Short Movies, Foreign and Other. For these genres, there is a significant difference in popularity across seasons.
- We cannot reject the null hypothesis for the following genres: Drama, Gay/Lesbian, Crime, Kids & Family and Special Interest. For these genres, there is no significant difference in popularity across seasons.

#### Monthly: 
![heatmapMonthly](https://github.com/user-attachments/assets/82eff270-41e8-4c2f-b4fc-009ef167dfc2)

H0: There is no significant difference in popularity of genres across months.

Ha: There is a significant difference in popularity of genres across months.

- We reject the null hypothesis for the following genres: Romance, Documentary, Action, Kids Family, Horror, Biography, Fantasy, LGBTQ+, Musical, Science Fiction, Western, Anime, Animation, Holiday, War, Music, Stand-up, Variety, Nature, Short, Sports, Entertainment, News, Foreign, Other, Gay-Lesbian, History. For these genres, there is a significant difference in popularity across months.
- We cannot reject the null hypothesis for the following genres: Adventure, Drama, Mystery Thriller, Comedy, Special Interest, Crime

### Visualization:
In order to determine genres with a clear trend of peaking in certain months/seasons, both the results of the monthly ANOVA test and a standard deviation scale above 10 was used. After filtering the resylts in this way, the following genres were found to be following a clear trend: War, Variety, Stand-up, Nature, Musical, LGBTQ+, Kids & Family, Horror, Gay-lesbian and Holiday. These genres were visualized with a line plot of trend over months, and can be found in the results folder of the Seasonal Trends. It's important to note that the peaks could be amplified by releases of certain movies as well. 

Some of the plots are as follows:
![image](https://github.com/user-attachments/assets/859d3a93-7137-49f4-b071-8a285bbcbd5b)
Holiday: The holiday genre's peak occuring in December reflects the increasing popularity of Christmas & Holiday themed movies during the period, which the New Years effect heavily impacting global masses contributes to. 

![horror](https://github.com/user-attachments/assets/2cf71acf-f2e7-4048-8dab-f8c39550eafe)
Horror: The horror genre peaking in October is likely due to Halloween, which is celebrated globally and is known to cause a peak in popularity in horror-themed products, and corresponds to October 31-November 1 every year. 

![lgbtq](https://github.com/user-attachments/assets/587e596d-1287-42a2-b5ca-cbe568514b28)
LGBTQ+: The peak of the genre occurs in June, which is the Pride Month dedicated to honoring LGBTQ+ individuals, and could be directly tied to this annual event. 

![musical](https://github.com/user-attachments/assets/d03996fc-87b6-454f-ba4f-8e8debc92fdb)
Musical: The peak of the Musical genre is at the end of the year - December and could be caused by year-end shows, new years' musicals and the festival energy surrounding crowds during this period.  

![nature](https://github.com/user-attachments/assets/db689f6e-8d27-4d43-abc8-31699cc009f2)
Nature: The nature genre seems to peak in June, start of the summer and the warmer months, and the increased interest in natural touristic locations & outdoor activities.

![war](https://github.com/user-attachments/assets/547ab875-7688-4255-80cf-e86ea1bca0a3)
War: Interest in war movies peaking in April could be tied to the majority of war movies that are globally popular take the World War I as their main topic and focus on the American side of the war. Other global events annually aligning with this month could also contribute to this data. 

# Machine Learning
Usage of features like audienceScore, tomatoMeter (critic score), genre, interest (peak popularity of genre) to create a model, testing accuracy to see if the model can predict box office revenue. Added a new feature (gap of critic-audience scores) to examine whether disagreement of audience and critics imply anything about box office revenue.
- Classification: binary classifier prediction of movies as low vs high box office revenue (higher/lower than median)
- Regression: predicting box office revenue in dollars

Regression RMSE: 6909439.59 (6.9 Million Dollars) - this value represents how far off the average prediction of the model is from the actual value of box office revenue. 6.9 million is a high value and could be due to the high variation value of the dataset

Precision: 0.63
Recall: 0.63
F1 Score: 0.63

Classification Accuracy: 0.63 - Model is predicting low/high box office revenue data correctly %63 of the time. %63 signifies that the prediction of the model is better than a completely random guess (of %50 correctness), yet it is not nearly accurate enough. This could be due to the features scores, genre or genre interest are not major predictors of box office revenue as supported by the test results done in the score vs box office revenue part of the project. (Accuracy was found to be %63 using logistic regresssion and %62 using random forest accuracy testing)
- Used weighted classes to ensure balance in low-high revenue classes.
- After applying cross validation, the classification accuracy remained nearly the same - we can conclude there is no overfitting.

## Findings: 
- As presented in the previous score vs box office data revenue part of the project, critic scores or audience scores are not strongly correlated with box office revenue.
- Applying machine learning methods such as binary classification, logistic regression, accuracy testing supported this finding; meaning even after including genre, genre interest or gap of critic-audience score features, it can be concluded that these features are not predictors of box office revenue data nor indicators of low or high box office revenue.

## Visualization
![RF Regression Actual-Predicted](https://github.com/user-attachments/assets/03b0fe5c-9ad5-4873-84b6-13b7317d5e54)
Random Forest Regression - Actual vs Predicted values of Box Office Revenue: Dense clustering near the 0 mark on the X axis (actual box office revenue values are densely clustered closer to 0 dollars) indicating that most of the movies in the dataset have low box office revenue. This is to be expected due to real life distribution where not many movies show huge box office success. It might also mean that the model might perform poorly when it comes to movies with overly high box office revenue (outliers) due to the heavy clustering on the opposite side. 

![Confusion Matrix](https://github.com/user-attachments/assets/dc708bad-b5fd-47d1-8667-ad6ed1bc8db1)
Confusion Matrix (using Heatmap): True Positive (597): 597 high box office predictions were high in observation as well. True Negatives (590): 590 low box office predictions were low in observation as well.  False Positives (361): 361 high box office predictions that were actually low in observation. False Negatives (360): 360 low box office predictions that were actually high in observation. The model identified movies more correctly than not (0.62-0.63). We can also note that the model was slightly better with classifying lower earning movies compared to higher revenue movies (outliers).

![Feature Importance](https://github.com/user-attachments/assets/a48a3391-836b-4462-8737-b4cacf086983)
Importance of Features (gap of scores, critic score, audience score, genres...): Ranking and distribution of importance of features show that out of all the features inclduded in the model, the best predictor of box office revenue was the gap of scores feature created by merging critic and audience score features during the feature engineering process. It was followed by critic scores and audience scores yet there is not big enough of a difference between these values to conclude that one of them is greatly better at predicting box office revenue compared to the other. 

## Limitations, Challenges, Future Work
Score vs box office revenue: The dataset originally consisted of over 140k+ movies; and cleaning out empty/missing values for box office, tomatometer and audience rating columns left out 13k+ movies. The great difference between the two values was mainly caused by the amount of rows of movies with no box office revenue data. This led to some of the dataset not being used. Additionally, some of the movies’ box office revenues were low enough to mean that their rating values might not have been accurate. Due to lack of popularity, a small amount of movies’ tomatometer (critic rating) value is 0, which could be tied to no critics reviewing the movie. This can also be said for movies with a small amount of voters which would affect the audience rating value.

Seasonal trend analysis: The greatest challenge in testing the relation between seasons/annual important dates and movie genres’ popularity was how frequently the system failed to fetch the requested data due to Google Trends’ 429 (TooManyRequests) error. My first approach to discover if there is an existing seasonal trend amongst genres was to request information from Google Trends for every single movie in the Rotten Tomatoes Movies dataset, but this approach proved to be unachievable due to how great the number of movies the dataset consisted of was. I moved on to requesting search data for genres instead, and used the Rotten Tomatoes dataset to create a list of movie genres and fetched data for these genres. Though the number was down from 130k+ to 20-30, the issue still persisted, and I had to move on to a retry based code to ensure I could retrieve data for the most number of genres possible. Genre names had to be cleaned due to special characters and NaN values corrupting data. Despite using the retry based mechanism, I had to improvise using sleep time as well to not overexhaust the system and prevent Trends from flagging my IP adress. Using the retry mechanism and delay times together, in the last retrieval attempt dated 25/04/2025, I was able to retrieve data for 33 out of 34 genres which left out data for only the “Sports & Fitness” genre. This was the most successful attempt and took 49 minutes and 6 seconds. Additionally, to prevent the context of search keywords and retrieving data of non-movies, I added the keyword “movies” to the end of the genre names retrieved from the Rotten Tomatoes dataset. 

Machine learning: sentiment analysis using IMDB reviews of movies was planned in the beginning of the project timeline, yet I wasn't able to attach/merge the data to the existing datasets due to the lack of features of the dataset (it was consisting of only reviews and their sentiments but lacked an identification feature like movie, genre, movie id, etc...). 
