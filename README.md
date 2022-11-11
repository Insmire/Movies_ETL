## Overview
The largest online retailer Amazing Prime Video is sponsoring a hackathon requesting participants to determine which low-budget movies will become popular box office films. Amazing Prime Video plans to obtain rights to the potentially popular movies for their streaming service. The purpose of this project is to assist their team in creating the list of movies to be used for the hackathon. To this end, I create a extract, transform, and load (ETL) pipeline to automate the data wrangling process. The pipeline is implemented on one dataset of all movies released after 1990 from Wikipedia and another dataset of movie ratings from MovieLens in Kaggle. The resulting clean data is stored within a SQL database.

---

## Resources
Data source (files exceed upload upload capacity):
  - wikipedia-movies.json
  - movies_metadata.csv
  - ratings.csv

Tools:
  - Anaconda
  - JSON
  - Jupyter Notebook
  - NumPy
  - Pandas
  - psycopg2
  - regular expressions (regex)
  - SQLAlchemy

---

## Results
The three files are extracted and read in Jupyter as dataframes.

wiki_movies_df

![wiki_movies_df](https://user-images.githubusercontent.com/96349090/198216496-d4a1db57-5291-4c5d-b1e6-3eada3221aa3.png)

movies_metadata_df

![kaggle_metadata_df](https://user-images.githubusercontent.com/96349090/198216534-8e05ea76-9e68-42f3-9c3d-d8deb0d484df.png)

ratings_df

![ratings_df](https://user-images.githubusercontent.com/96349090/198216572-e8f7068b-ce8f-47ee-b671-4a1b2ca7dbba.png)

The dataframes are then transformed by using a try-except block to catch errors, filtering for specific values with regualr expressions, deleting unreadable rows or columns, and cleaning any null values.

transformed wiki_movies_df



transformed movies_metadata_df



transformed ratings_df


All three dataframes are merged to create a single dataframe, movies_with_ratings_df, and added to a SQL database.

As shown below, filtering the available movies via the ETL pipeline shows that there are a total of 6052 movies that may become popular box office films. Each movie within the SQL table contain 31 columns of information including IMDB ID, Kaggle ID, title, original title, tagline, Wikipedia URL, IMDB link, runtime, budget, etc. The unique identifier is the IMDB ID.

![movies_query](https://user-images.githubusercontent.com/96349090/195522131-0b5cad0e-85c5-45bf-bd22-c07bbd0fbfe0.png)

A total of 26,024,289 of ratings are available as shown below from SQL query.

![ratings_query](https://user-images.githubusercontent.com/96349090/195522238-f3900f70-5023-4446-8db9-f9ded8449306.png)

<!-- ETL code screenshot -->

<!-- ## Summary -->
