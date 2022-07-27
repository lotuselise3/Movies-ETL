# Movies-ETL

## Module 8 Challenge ~ ETL Wikipedia and Kaggle Metadata
---
## Overview of Project
- In this module, we learned how to use the Extract, Transform, Load (ETL) process to create data pipelines, moving data from a source (such as Kaggle) to a destination (such as SQL database), and transforming the data along the way. To break it down further, we extracted several movie data using Python, cleaned and transformed data using Pandas, and used regular expressions to parse data and transform text into numbers. Lastly, we loaded the cleaned data into PostgreSQL to be able to predict popular films for a streaming service. 
### Purpose
- Looking into Wikipedia data, Kaggle metadata, and the MovieLens rating data, I performed an ETL process to create an automated pipeline for Amazing Prime. 

---
**Deliverable 1 ~ Write an ETL Function to Read Three Data Files**
### EXTRACTING
**Referring to... _ETL_function_test.ipynb_ file** 

- Using Python, Pandas, the ETL process --> reading in the Wikipedia movie JSON, Kaggle metadata and MovieLens ratings CSV files --> creates three DataFrames

*Wikipedia Movies JSON file, starting with 193 Columns:*
![wiki-movies-df-DataFrame_1](https://user-images.githubusercontent.com/68654746/181340388-817d120c-1427-49b8-ae0f-0a0ff2cf073b.png)

*Kaggle Movie Metadata, 24 columns*
![kaggle-metadata-DataFrame](https://user-images.githubusercontent.com/68654746/181341109-0899ad0a-ae93-4f20-b4d5-fb128c591cf6.png)

*Kaggle Ratings data, 2602489 rows by 4 columns* 

![ratings-DataFrame](https://user-images.githubusercontent.com/68654746/181341139-354211d5-2b02-41da-ab02-f6b472098cd1.png)
---
**Deliverable 2** ~ Extract and Transform the Wikipedia Data**
### TRANSFORMING
**Referring to... _ETL_clean_wiki_movies.ipynb_ file** 

- Extracting the IMDb IDs using a regular expression string and dropping duplicates by using a try-except block to catch errors 
- Clean the box office data, the budget data, the release date, and the running time  
*Wikipedia Movies transformed, 22 columns* 
<img width="546" alt="d2_wiki_movies" src="https://user-images.githubusercontent.com/68654746/181343071-9346c0e6-44da-4faa-b731-b859274f06ce.png">

*Wikipedia Movies, making the column names more succinct and uniform, 7033 rows of data* 

<img width="194" alt="d2_wiki_movie_counts" src="https://user-images.githubusercontent.com/68654746/181343092-d76ee710-7424-4200-a25e-4f1ab4816378.png">

---
**Deliverable 3** ~ Extract and Transform the Kaggle Data**
### TRANSFORMING
**Referring to... _ETL_clean_kaggle_data.ipynb_ file** 

*Merged the Kaggle metadata DataFrame with the Wikipedia movies DataFrame to create the movies_df DataFrame* 
![d3_movies-df](https://user-images.githubusercontent.com/68654746/181346221-ca12b2e1-8520-46f2-b232-c258290d263a.png)

*Merged the MovieLens rating data DataFrame with the movies_df DataFrame to create the movies_with_ratings_df* 
![d3_movies-with-ratings-df](https://user-images.githubusercontent.com/68654746/181346236-baf3a42c-4ee7-4b1c-8de0-2a12263a64fa.png)

---
**Deliverable 4** ~ Create the Movie Database**
### LOADING
**Referring to... _ETL_create_database.ipynb_ file**
- Adding the movies_df DataFrame and MovieLens rating CSV data to a SQL database --> Creating the Movie Database

*Sending the data to PostgresSQL* 

<img width="509" alt="d4_final_send" src="https://user-images.githubusercontent.com/68654746/181347561-4f63fd87-99ab-488c-b52c-c7022328cdda.png">

*Verifying the data in PgAdmin* 

![d4_movie_data_count](https://user-images.githubusercontent.com/68654746/181347547-f39e7b80-3beb-4b4a-a5d0-fd6592d9854e.png)

<img width="271" alt="d4_ratings_query" src="https://user-images.githubusercontent.com/68654746/181347452-fd584caf-32a3-49b2-9851-a7e1ef3f43dd.png">

