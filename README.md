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
As shown below, filtering the available movies via the ETL pipeline shows that there are a total of 6052 movies that may become popular box office films. Each movie within the SQL table contain 31 columns of information including IMDB ID, Kaggle ID, title, original title, tagline, Wikipedia URL, IMDB link, runtime, budget, etc. The unique identifier is the IMDB ID.

movies screnenshot

ratings screenshot

---

## Summary
