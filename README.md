# STQD6324 Data Management Assignment 2

## MovieLens Data Analysis using Apache Spark and Cassandra

**Name:** Yang Huan
**Matric Number:** P161796
**Course:** STQD6324 Data Management
**Semester:** Semester 2 2025/2026

---

## Important Note

This assignment was completed using **Apache Zeppelin**. Therefore, the notebook file in this repository is provided in **Zeppelin JSON format**, not Jupyter Notebook format.

The JSON file may not display like a normal notebook directly on GitHub. To view the complete notebook with code, outputs, tables and visualizations, please download the JSON file and import it into Apache Zeppelin.

---

## Project Overview

This project analyzes the **MovieLens 100K dataset** using **Apache Spark** and **Apache Cassandra**.

The main objective of this assignment is to build a data processing and analysis workflow that loads MovieLens data from HDFS, processes the data using Spark RDDs and DataFrames, stores the processed data into Cassandra, reads the data back from Cassandra, and performs analytical queries using Spark SQL.

The analysis focuses on movie ratings, top-rated movies, active users' favourite genres, younger users, and users with a specific occupation and age range.

---

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

---

## Software Environment

The assignment was developed using the following environment:

| Component            | Version / Description               |
| -------------------- | ----------------------------------- |
| Apache Spark         | 2.3.0.2.6.5.0-292                   |
| Cassandra            | 3.11.19                             |
| Notebook Environment | Apache Zeppelin                     |
| Data Storage         | HDFS and Cassandra                  |
| Programming Language | Scala in Zeppelin Spark interpreter |

---

## Dataset Description

The dataset used in this assignment is the **MovieLens 100K dataset**. Three required files were used:

| File     | Description                                                                       |
| -------- | --------------------------------------------------------------------------------- |
| `u.user` | Contains user information such as user ID, age, gender, occupation and zip code   |
| `u.data` | Contains movie rating records such as user ID, movie ID, rating and timestamp     |
| `u.item` | Contains movie information such as movie ID, title, release date and movie genres |

The dataset contains:

* 943 users
* 100,000 rating records
* 1,682 movies

---

## Project Workflow

The workflow of this assignment is:

1. Upload the MovieLens 100K dataset into HDFS.
2. Load `u.user`, `u.data` and `u.item` from HDFS into Spark.
3. Create Spark RDDs from the raw dataset files.
4. Transform the RDDs into Spark DataFrames.
5. Perform basic data cleaning and preprocessing.
6. Write the processed DataFrames into Cassandra tables.
7. Read the Cassandra tables back into Spark DataFrames for validation.
8. Perform analytical queries using Spark SQL.
9. Present the results using tables and a rating distribution visualization.
10. Provide discussion and interpretation for the analysis results.

---

## Cassandra Storage

The processed Spark DataFrames were written into Cassandra using the keyspace `movielens`.

| Spark DataFrame | Cassandra Keyspace | Cassandra Table |
| --------------- | ------------------ | --------------- |
| `usersDF`       | `movielens`        | `users`         |
| `ratingsDF`     | `movielens`        | `ratings`       |
| `moviesDF`      | `movielens`        | `movies`        |

After writing the data into Cassandra, the tables were read back into Spark DataFrames to validate that the storage process was successful.

---

## Analytical Tasks Completed

The following analytical tasks were completed in the Zeppelin notebook:

### 1. Average Rating for Each Movie

The average rating for each movie was calculated by joining the ratings data with the movie information. This helps show the overall rating performance of each movie.

### 2. Top Ten Movies with the Highest Average Ratings

The top ten movies with the highest average ratings were identified. To make the ranking more meaningful, only movies with at least 50 ratings were considered.

### 3. Favourite Genre of Active Users

Users who rated at least 50 movies were identified as active users. For each active user, the favourite movie genre was determined based on the genre they rated most frequently.

### 4. Users Below 20 Years Old

All users whose age is less than 20 years old were filtered from the user dataset.

### 5. Scientists Aged Between 30 and 40

Users whose occupation is `scientist` and whose age is between 30 and 40 years old were identified.

---

## Result Summary

The main results of the analysis are summarized below:

| Analytical Task                 | Result Summary                                                                                                |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Average rating for each movie   | Average ratings were calculated for movies using Spark SQL                                                    |
| Top ten movies                  | Top-rated movies were identified using average rating and rating count                                        |
| Favourite genre of active users | Active users were identified based on at least 50 ratings, and their most frequently rated genre was selected |
| Users below 20 years old        | 77 users were found to be less than 20 years old                                                              |
| Scientists aged 30 to 40        | 16 users were found with occupation `scientist` and age between 30 and 40                                     |

---

## Visualization

A rating distribution visualization was included in the Zeppelin notebook.

The visualization shows the number of ratings for each rating score from 1 to 5. The result shows that most ratings are between 3 and 5, which suggests that users generally gave moderate to positive ratings. Lower ratings such as 1 and 2 appeared less frequently.

---

## How to View the Assignment Notebook

Because this assignment was completed in Apache Zeppelin, the notebook is exported as a JSON file.

To view the full assignment:

1. Download the file `YANG HUAN assignment 2.json` from this GitHub repository.
2. Open Apache Zeppelin.
3. Click **Import note**.
4. Upload the downloaded JSON file.
5. Open the imported notebook in Zeppelin.
6. The code, results, tables, discussions and visualization can then be viewed inside Zeppelin.

Note: The JSON file is not intended to be read directly on GitHub. It should be imported into Apache Zeppelin for proper viewing.

---

## Repository Contents

| File                          | Description                                                                             |
| ----------------------------- | --------------------------------------------------------------------------------------- |
| `YANG HUAN assignment 2.json` | Exported Apache Zeppelin notebook containing the full assignment                        |
| `README.md`                   | Explanation of the project, workflow, results and instructions for viewing the notebook |

---

## Conclusion

This assignment successfully demonstrates the integration of Apache Spark and Cassandra for big data management and analysis. The MovieLens 100K dataset was loaded from HDFS, processed using Spark RDDs and DataFrames, stored into Cassandra, retrieved for validation, and analyzed using Spark SQL.

The analysis results show how Spark can be used for distributed data processing, while Cassandra can be used as a storage layer for structured analytical data.
