# Movies-ETL

## Overview of Project 

### Purpose

The purpose of this analysis is creating an automated pipeline, where new data will undergo appropriate transformations, and be loaded into existing tables.\
The approach is to create one function, whose input parameters will include the following files:
- Wikipedia json file containing data on movies from 1990 to 2018.
- A Kaggle metadata file with movie data.
- A MovieLens dataset of over 20 million reviews.

The function will perform the ETL process on the above files, and add the data to PostgreSQL database. 

### Resources used
- Data Source : wikipedia-movies.json, movies_metada.csv (Kaggle), ratings.csv(Kaggle)
- Software : Python 3.7.9, Jupyter Notebook 6.1.4, Pandas 1.1.3, Numpy 1.17.0, Anaconda 1.7.2, 


## Results
Fig. of the cleaned and merged movie data set.
<Add figure>
Fig. of the cleaned and merged movie data set with the ratings.
<add figure>
Fig showing completion of the upload process of the Ratings data to the database, along with the time it took to upload each section.
<add figure>

## Summary 
The analysis was performed in stages.
- The first deliverable is creating a function to read the three datafiles and inspect if they were loaded correctly.
- The second deliverable consists of creating a function that extracts and transforms the Wikipedia Data, and displays the transformed DataFrame, and the columns\
Note that after transforming the columns Box office, Budget, Release date, and Running time, and storing their values in new columns, I have dropped all the old columns (instead of just the two - Box office, and Running time, as suggested in the challenge). The reason being none of the original columns have any further need to be kept.
- The third deliverable consisted of extracting and transforming the Kaggle data (both the movies and the rating data).\
Then the Kaggle movies data and the wikipedia data is merged, and the appropritate columns are kept, and wherever required null vlaues were filled in with data from the corresponding columns from the appropritate dataset.\
The cleaned movie dataset was then merged with the cleaned and transformed ratings dataset, to have the ratings information for the corresponding movies in the movie dataset.\
(Please refer to the figures under results for the cleaned and merged movies DataFrame, and the movies_with_ratings DataFrame.)\
- The fourth and last deliverable included combining all the analysis done previously to obtain the clean and merged DataFrames, and then loading them into the PostgreSQL database.\
The ratings data was also uploaded to the database to be made available for aditional analysis, if required. The ratings data being too large, was uploaded in chunks. See Fig under Results section showing the time taken to upload the ratings data in "chuncks" to the database.
