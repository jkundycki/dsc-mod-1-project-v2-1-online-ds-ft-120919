# Finding Success in the Movie Industry
## What does the Data tell us?

![](images/theme.webp)


### Outline
* [Goals and Overview](##goals-and-overview)
* [Final Thoughts](#final)

## Goals and Overview

In this project, I was given multiple datasets
* /zippedData/tmdb.movies.csv
* /zippedData/imdb.title.crew.csv
* /zippedData/tn.movie_budgets.csv
* /zippedData/imdb.title.ratings.csv
* /zippedData/imdb.name.basics.csv
* /zippedData/imdb.title.principals.csv
* /zippedData/imdb.title.akas.csv
* /zippedData/bom.movie_gross.csv
* /zippedData/imdb.title.basics.csv

The goal of this project is to conduct data analysis and create a presentation that explores what type of films are currently doing best in the box office. The findings must then be translated into actionable insights that could be used when creating a film that could increase the likelihood of a successful release.


------

<details><summary><span style="font-size:18pt; font-weight:bold">Question 1: Are there any noticeable trends in the data in terms of profit and profitability?</span>



# Exploration (EDA)
In the image below, we can see that the top highest grossing movies when compared to their production budget movies are: 
* Avatar 
* Titanic
* Avengers: Infinity War
* Star Wars Ep. VII: The Force Awakens
* Jurassic World

I decided to look at the distribution of **genres** across the **top 50** movies

# Some code I used to aggregate the genres by counts

```python
genre_count = {}
for movie in top_5_budget_gross_diff_movies:
    movie_genres = joined_df[joined_df['movie']==movie]['genres'].values[0]
    try:
        for genre in movie_genres:
            genre_count[genre] = genre_count.get(genre, 0) + 1
    except:
        genre_count['not_listed'] = genre_count.get('not_listed', 0) + 1

genre_count
```

![](images/profit.png)

![](images/profitmargin.png)
</details>

### Q1: Insights/Findings/Recommendations

**Findings**

After examining the top 50 movies for gross profit and gross profit margin, I found that 88% of the top 50 gross profit movies were sequels, prequels, remakes or built upon well established, extremely succesfully movie franchises and studios.
98% of the top 50 gross profit margin movies were novel concepts or ideas that were not built upon an already existing movie.

**Recommendations**
* Purchase well established franchise and create new movies upon the franchise for largest dollar amount returns.
* Create a movie from a succesful, original idea for best return on investment 


**Next Steps**
* Explore genres to see what genres tend to have the highest profit margin

<details><summary><span style="font-size:18pt; font-weight:bold">Question 2: Assuming we were to start a new movie from scratch, are there any trends that can help our movie have a high profit margin? Let's start by investigating if there are any trends for genre.</span>



# Exploration (EDA)
In the image below, we can see that the top highest grossing movies when compared to their production budget movies are: 
* Avatar 
* Titanic
* Avengers: Infinity War
* Star Wars Ep. VII: The Force Awakens
* Jurassic World

I decided to look at the distribution of **genres** across the **top 50** movies

# Some code I used to aggregate the genres by counts

```python
genre_count = {}
for movie in top_5_budget_gross_diff_movies:
    movie_genres = joined_df[joined_df['movie']==movie]['genres'].values[0]
    try:
        for genre in movie_genres:
            genre_count[genre] = genre_count.get(genre, 0) + 1
    except:
        genre_count['not_listed'] = genre_count.get('not_listed', 0) + 1

genre_count
```

![](images/q1-barchart.png)
</details>

### Q2: Insights/Findings/Recommendations

**Findings**

After examining the top 500 movies for gross profit margin, I found the three most represented movie genres were Drama, Comedy and Horror (in order).

**Recommendations**
* If creating a new movie, use one of the genres from the findings (Drama, Comedy, Horror...) to increase chance of a higher profit margin
* Attempt to gather more data for more accurate results and better analysis; many of the data points did not have a genre listed


**Next Steps**
* Explore if there are advantageous release months for our most succesful genres in terms of top profit margin

<details><summary><span style="font-size:18pt; font-weight:bold">Q3: Are there any trends for the highest profit margin movies based on genre?</span>



# Exploration (EDA)
In the image below, we can see that the top highest grossing movies when compared to their production budget movies are: 
* Avatar 
* Titanic
* Avengers: Infinity War
* Star Wars Ep. VII: The Force Awakens
* Jurassic World

I decided to look at the distribution of **genres** across the **top 50** movies

# Some code I used to aggregate the genres by counts

```python
genre_count = {}
for movie in top_5_budget_gross_diff_movies:
    movie_genres = joined_df[joined_df['movie']==movie]['genres'].values[0]
    try:
        for genre in movie_genres:
            genre_count[genre] = genre_count.get(genre, 0) + 1
    except:
        genre_count['not_listed'] = genre_count.get('not_listed', 0) + 1

genre_count
```

![](images/q1-barchart.png)
</details>

### Q3: Insights/Findings/Recommendations

**Findings**

After examining the release months of the top margin movie genres (Drama, Comedy, Horror) against all the movies for those same genres, I found that top profit margin horror movies tended to be released in October, top profit margin drama movies tended to be released in June and November compared to all movies of those genres. Top profit margin comedy movies tended to be released in June and July like their counterparts, but tended to trend towards those months more strongly than their counterparts.

**Recommendations**
* Collect genre information for all movies
* If creating a movie in the lowest performing genres, do not expect to gross over the budget.  
* If aiming at high gross, create action adventures movies.


**Next Steps**
* More in-depth statistical analysis for better understanding of the trends.  
* Same as for question 2, attempt to gather more genre data as many movies did not have any listed.
