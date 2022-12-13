## Overview
The largest online retailer Amazon Prime Video is sponsoring a hackathon requesting participants to determine which low-budget movies will become popular box office films. Amazon Prime Video plans to obtain rights to these potentially popular movies for their streaming service. The purpose of this project is to assist their team in creating the list of movies to be used for the hackathon. To this end, I created an extract, transform, and load (ETL) pipeline to automate the data wrangling process. I then implemented the pipeline on one dataset of all movies released after 1990 from Wikipedia and another dataset of movie ratings from MovieLens in Kaggle. Lastly, I stored the resulting clean data within a SQL database.

---

## Resources
Data source (files exceed upload capacity):
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
As shown below, I extracted and read the three files in Jupyter as DataFrames.

| wiki_movies_df | movies_metadata_df | ratings_df |
| :---: | :---: | :---: |
| ![wiki_movies_df](https://user-images.githubusercontent.com/96349090/198216496-d4a1db57-5291-4c5d-b1e6-3eada3221aa3.png) |  ![kaggle_metadata_df](https://user-images.githubusercontent.com/96349090/198216534-8e05ea76-9e68-42f3-9c3d-d8deb0d484df.png) | ![ratings_df](https://user-images.githubusercontent.com/96349090/198216572-e8f7068b-ce8f-47ee-b671-4a1b2ca7dbba.png) |

I then transformed the DataFrames by using a try-except block to catch errors, refactoring code, filtering for specific values with regular expressions, deleting unreadable rows or columns, and cleaning any null values.

I merged the DataFrames wiki_movies_df and movies_metadata_df into a new DataFrame movies_df.

movies_df

![transformed_movies_df](https://user-images.githubusercontent.com/96349090/204075400-cbc10833-4b95-4d21-9005-fa6230f52b48.png)

I added movies_df to a SQL database along with ratings_df as tables named movies and ratings.

As shown below, filtering the available movies via the ETL pipeline shows that a total of 6052 movies have potentiality to become established box office films. Each movie within the SQL table contains 31 columns of information, including IMDB ID, Kaggle ID, title, original title, tagline, Wikipedia URL, IMDB link, runtime, budget, etc. The unique identifier is the IMDB ID.

A total of 26,024,289 ratings are available, as shown below from the SQL query.

| movies_df | ratings_df |
| :---: | :---: |
| ![movies_query](https://user-images.githubusercontent.com/96349090/195522131-0b5cad0e-85c5-45bf-bd22-c07bbd0fbfe0.png) | ![ratings_query](https://user-images.githubusercontent.com/96349090/195522238-f3900f70-5023-4446-8db9-f9ded8449306.png) |

---

### Contact

Email: show.wang94@gmail.com

LinkedIn: [https://www.linkedin.com/in/show-kate-w-802b36168](https://www.linkedin.com/in/show-kate-w-802b36168)
