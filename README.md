# MovieLens Data Analysis using Apache Spark and Cassandra

## Assignment Information

**Course:** STQD6324 Data Management
**Assignment:** Assignment 2
**Semester:** Semester 2 2025/2026
**Name:** Yang Huan
**Matric Number:** P161796

## Project Overview

This project analyzes the MovieLens 100K dataset using Apache Spark and Cassandra. The assignment was completed in Apache Zeppelin and exported as a JSON notebook file.

The main purpose of this project is to demonstrate a big data processing workflow that includes loading data from HDFS, creating Spark RDDs, transforming RDDs into DataFrames, storing processed data into Cassandra, reading data back from Cassandra, and performing analytical queries using Spark SQL.

## Technologies Used

The following technologies were used in this assignment:

* Apache Zeppelin
* Apache Spark
* Spark RDD
* Spark DataFrame
* Spark SQL
* HDFS
* Apache Cassandra
* Spark Cassandra Connector
* MovieLens 100K Dataset

## Software Environment

The assignment was developed using the following environment:

* Apache Spark version: 2.3.0.2.6.5.0-292
* Cassandra version: 3.11.19
* Notebook environment: Apache Zeppelin
* Data storage: HDFS and Cassandra

## Dataset Description

The dataset used in this project is the MovieLens 100K dataset. Three files from the dataset were used:

| File     | Description                                                                                 |
| -------- | ------------------------------------------------------------------------------------------- |
| `u.user` | Contains user demographic information such as user ID, age, gender, occupation and zip code |
| `u.data` | Contains movie rating records including user ID, movie ID, rating and timestamp             |
| `u.item` | Contains movie information such as movie ID, title, release date and genre indicators       |

The dataset contains:

* 943 users
* 100,000 rating records
* 1,682 movies

## Project Workflow

The workflow of this assignment is as follows:

1. Load the MovieLens dataset files from HDFS.
2. Create Spark RDDs from the raw dataset files.
3. Transform the RDDs into Spark DataFrames.
4. Perform basic data cleaning and preprocessing.
5. Write the processed DataFrames into Cassandra tables.
6. Read the Cassandra tables back into Spark DataFrames for validation.
7. Perform analytical queries using Spark SQL.
8. Present the results using tables and a rating distribution visualization.
9. Provide interpretation and discussion for each analytical task.

## Cassandra Tables

The following DataFrames were written into Cassandra:

| DataFrame   | Cassandra Keyspace | Cassandra Table |
| ----------- | ------------------ | --------------- |
| `usersDF`   | `movielens`        | `users`         |
| `ratingsDF` | `movielens`        | `ratings`       |
| `moviesDF`  | `movielens`        | `movies`        |

The data was then read back from Cassandra into Spark DataFrames to validate that the storage process was successful.

## Analytical Tasks

The assignment includes the following analytical tasks:

### 1. Average Rating for Each Movie

This task calculates the average rating for each movie based on all user ratings. The result helps identify how each movie performed overall in the MovieLens dataset.

### 2. Top Ten Movies with the Highest Average Ratings

This task identifies the top ten movies with the highest average ratings. To make the result more reliable, movies with at least 50 ratings were considered. This avoids ranking movies highly only because they received very few ratings.

### 3. Favourite Genre of Active Users

This task identifies users who rated at least 50 movies and determines their favourite movie genre based on the genre they rated most frequently. The result shows the most common genre preference for active users.

### 4. Users Below 20 Years Old

This task filters all users whose age is less than 20 years old. The result provides a subset of younger users in the MovieLens dataset.

### 5. Scientists Aged Between 30 and 40

This task identifies users whose occupation is `scientist` and whose age is between 30 and 40 years old. The result provides a more specific demographic group from the user dataset.

## Result Summary

The main results obtained from the analysis are summarized below:

| Analytical Task                 | Summary                                                                                                       |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Average rating for each movie   | Average ratings were calculated by joining the ratings and movies tables                                      |
| Top ten movies                  | The highest-rated movies were identified using average rating and total rating count                          |
| Favourite genre of active users | Active users were identified based on at least 50 ratings, and their most frequently rated genre was selected |
| Users below 20 years old        | 77 users were found to be less than 20 years old                                                              |
| Scientists aged 30 to 40        | 16 users were found with occupation `scientist` and age between 30 and 40                                     |

## Visualization

A rating distribution visualization was included in the Zeppelin notebook. The visualization shows the number of ratings for each score from 1 to 5.

The rating distribution shows that most ratings are between 3 and 5, which suggests that users generally gave moderate to positive ratings. Lower ratings such as 1 and 2 appeared less frequently.

## How to View the Notebook

This assignment was completed using Apache Zeppelin and exported as a JSON file.

To view the notebook:

1. Download the file `YANG HUAN assignment 2.json` from this GitHub repository.
2. Open Apache Zeppelin.
3. Click **Import note**.
4. Upload the JSON file.
5. Open the imported notebook in Zeppelin.

Note: The JSON file may not display like a normal Jupyter Notebook directly on GitHub. It should be imported into Apache Zeppelin to view the full notebook structure, code, outputs and visualizations.

## Repository Files

This repository contains:

| File                          | Description                                                     |
| ----------------------------- | --------------------------------------------------------------- |
| `YANG HUAN assignment 2.json` | Exported Apache Zeppelin notebook for Assignment 2              |
| `README.md`                   | Project explanation, workflow, results summary and instructions |

## Conclusion

This assignment successfully demonstrates the use of Apache Spark and Cassandra for big data processing and analysis. The MovieLens 100K dataset was loaded from HDFS, processed using Spark RDDs and DataFrames, stored into Cassandra, retrieved for validation, and analyzed using Spark SQL.

The results show that Spark and Cassandra can be integrated effectively for distributed data processing, storage and analytical querying.
