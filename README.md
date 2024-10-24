![dataset cover](./images/overview.jpg)

# Movie Performance Analysis

## Overview

This project analyzes the performance of movies using ROI (Return on Investment), Revenue, and Ratings metrics to guide a new movie studio in making informed decisions about the most profitable genres, budgets, and runtimes. The data is sourced from the im.db SQLite database and a Kaggle dataset that contains comprehensive movie statistics, including financial details, runtime, and ratings.

## Business Understanding
![business problem cover](./images/business.jpg)

### Business Problem

Your company now sees all the big companies creating original video content and they want to get in on the fun. They have decided to create a new movie studio, but they don’t know anything about creating movies. You are charged with exploring what types of films are currently doing the best at the box office. You must then translate those findings into actionable insights that the head of your company's new movie studio can use to help decide what type of films to create.

### Stakeholder

The primary stakeholder is the new movie studio, aiming to create original movie content and optimize investments by selecting movie types (genres, budgets, and runtimes) that yield the highest financial returns and audience engagement.

### Key Business Questions

1. Which Movie Genres Are the Most Profitable in Terms of ROI and Revenue?
   - Identifying the genres that provide the highest financial returns and audience appeal.
2. How Does Production Budget Impact Movie Success Metrics (Ratings, ROI, and  Revenue)?
   - Exploring how budget size correlates with movie success metrics to optimize spending.
3. How Does Runtime Affect Success Metrics and Viewer Engagement?
   - Investigating whether runtime influences success metrics like ratings and audience engagement (votes).

   ** Success Metrics
   *** Revenue: Total box-office income (Worldwide gross).
   *** ROI: A profitability metric calculated as ;
      - ROI = Worldwide Revenue−Production Budget / Production Budget 
   *** Ratings: The average rating a movie receives (provided as a pre-calculated value in the dataset).

## Data Understanding

### Source of Data

1. im.db : An SQLite database containing movie information, including movie basics, directors, ratings, and people involved in movie production.
   - Tables : movie_basics, directors, movie_ratings, persons, principals, movie_akas, and more.
   - * `im.db.zip`
  * Zipped SQLite database (you will need to unzip then query using SQLite)
  * `movie_basics` and `movie_ratings` tables are most relevant

![Tables](./images/movie_data_erdness.jpeg)

2. Kaggle dataset: The dataset from Kaggle offers additional movie statistics.
   - This dataset provides comprehensive movie statistics compiled from multiple sources, including Wikipedia, The Numbers, and IMDb.

### Description of Data

1. movie_title: The title of the movie.
2. production_budget: The production budget.
3. worldwide_gross: Total revenue worldwide.
4. domestic_gross: Total revenue in domestic markets.
5. runtime_minutes: Movie duration.
6. genres: Movie genres.
7. average_rating: IMDb average rating.
8. number_of_votes: Number of votes/reviews on IMDb.

### Data Cleaning and Transformation 

1. Merged Data: Merged data from im.db and Kaggle based on common fields.
2. Handling Missing Values: Addressed missing values by imputation or removal.
3. Splitting Genres: Split the genres column to handle movies with multiple genres.
4. Removed Duplicates: Eliminated duplicate entries to ensure accuracy.
5. To determine the most profitable genres, we calculated both the ROI and Revenue for each genre.
6. We examined the correlation between production budget and success metrics (i.e., revenue, ROI, and ratings). And a regression analysis was performed to investigate how budget affects both revenue and ROI.
7. The relationship between movie runtime and viewer engagement (votes, ratings) and revenue was explored to identify whether longer movies tend to perform better. And we conducted a t-test to compare the impact of short vs. long runtimes on revenue and audience engagement.

## Analysis and Visualizations

Top 10 Movies by ROI : Horror and Thriller movies, which generally have lower production budgets, consistently deliver the highest ROI.

picture

Average ROI by Genre : Horror, Thriller, and Comedy genres deliver the highest ROI, while genres like Action and Adventure tend to have lower ROI but higher revenue.

picture

Revenue by Genre : Action, Adventure, and Sci-Fi genres generate the highest revenue, indicating that these genres are ideal for high-budget, global releases.

picture

Budget vs. Worldwide Gross Revenue : Movies with larger budgets tend to generate significantly more revenue. However, the return on investment (ROI) does not increase proportionally with budget.

picture

Correlation Heatmap: Budget, ROI, and Revenue : There is a strong positive correlation between budget and revenue, but a weak correlation between budget and ROI, suggesting that spending more does not guarantee higher profitability.

picture


Runtime vs. Audience Engagement (Votes) : Longer movies tend to attract more audience engagement (measured by votes). However, the relationship between runtime and ratings is weak, meaning longer movies don't necessarily score better with audiences.

Average Revenue for Short vs. Long Runtime : Movies with longer runtimes generate more revenue, likely due to their association with bigger, more expensive productions. However, these films are not always more profitable in terms of ROI.

## Conclusions

- **Most Profitable Genres**:  
 Genres like Horror and Thriller deliver higher ROI with lower production costs, making them ideal for profitability. Genres like Horror and Thriller are safer, low-budget investments that often yield higher ROI.

- **Impact of Budget on Success Metrics**:  
 High-budget movies such as Action and Sci-Fi generate more revenue but do not always result in better ROI. For studios with limited resources, low-budget films can be safer investments. Action and Fantasy films tend to generate significant box-office revenue, making them ideal for larger investments.

- **Runtime and Audience Engagement**:  
 Movies with runtimes between 90 and 120 minutes yield the best balance between engagement (votes) and ratings, making this the optimal runtime range. Movies with runtimes between 90 and 120 minutes strike the best balance between engagement and profitability.

### **Additional Insights**

- **Director Experience and ROI**: 
Directors with more experience tend to achieve higher ROI, especially in Drama and Biography genres.

- **Award Influence on Revenue**: 
Winning prestigious awards like Oscars increases movie revenue but not necessarily ROI due to higher production costs.

- **Genre Trends Over Time**: 
Genres like Superhero and Sci-Fi have grown in popularity over the years, suggesting studios should tap into these trends.

### **Overall Stragic Enhancements**

- **Balanced Genre Strategy**: 
The studio should focus on a mix of high-revenue genres like Action and low-budget, high-ROI genres like Horror.

- **Leverage Director Expertise**: 
Hiring experienced directors, particularly for mid-budget films, will enhance ROI and overall profitability.

- **Optimized Movie Length**: 
Prioritize movies with runtimes of 90 to 120 minutes to maximize audience engagement and ratings.


### Next Steps

- **Director Influence on ROI**:  
 Explore how directors' past performances impact ROI.

- **Awards and Success Metrics**:  
 Investigate how winning awards affects movie ratings and long-term profitability.

- **Trends in Genre Popularity**:  
  Study how genre preferences shift over time and predict future trends in audience demand.

## For More Information

See the full analysis in the [Jupyter Notebook](https://github.com/) or review this [presentation](https://github.com/)

[Tableau Dashboard link ](https://public.tableau.com/views/JSPhase2Project_1/Dashboard2?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

[Original data source from Kaggle](https://www.kaggle.com/datasets/alessandrolobello/the-ultimate-film-statistics-dataset-for-ml/data)

## Repository Structure 

```
├── dashboard
├── images
├── notebooks
├── presentation
├── zippedData
├── .gitignore