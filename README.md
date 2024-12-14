# Capstone_Project_Netflix
## Problem Statement

- Customer Behaviour and it's prediction lies at the core of every Business Model. From Stock Exchange, e-Commerce and Automobile to even Presidential Elections, predictions serve a great purpose. Most of these predictions are based on the data available about a person's activity either online or in-person.
- Recommendation Engines are the much needed manifestations of the desired predictability of user activity. Recommendation Engines move one step further and not only give information but put forth strategies to further increase users' interaction with the platform.
- In today's world OTT platform and Streaming Services have taken up a big chunk in the Retail and Entertainment industry. Organizations like Netflix, Amazon etc. analyse User Activity Pattern's and suggest products that better suit the user needs and choices.

---
## Project Objective 

The purpose of this Project Project we will be
creating one such Recommendation Engine
from the ground-up, where every single user,
based on there area of interest and ratings,
would be recommended a list of movies that
are best suited for them.

---

## Data Description:

- The dataset is taken from kaggle known as netflix prize dataset and is in specific format.
- So we have to use pandas slicing to get the data from the dataset in a required format.
- Provided format is of rows 24058263 and columns 2 having headers 0 and 1.
- Where 0th columns contains both customer Id and movie Id for the individual customer and 1st column contains movie ratings.
- After the manipulation of provided dataset we get 24058262 rows and 3 columns
    - *Customers Id*:- Columns contains customer Ids
    - *Movies Id*:- Have Ids of the corresponding movies.
    - *Ratings*:- Contains ratings of movies given by particular individuals.
- There are another dataset contaning movies titles for the particular movie Id.
    - *Movies Id*:- Have Ids of the corresponding movies.
    - *Year*:- The year of movies release.
    - *Name*:- Name of the movie.
 
--- 

## Data Preprocessing

The pre-processing of the data included the following steps:
1. Step 1: Load Data
2. Step 2: Perform ***Exploratory Data Analysis***
    - Confirm number of records in the data and how they are distributed
    - Check for missing data, invalid entries, duplicates
    - Check for data arrangement and how they are present as all necessary columns are provided.
    - In this case as given below:-
        - Provided Dataset:-

          ![](Images/image01.png)
          ![](Images/image03.png)
        - Corrected Dataset:-

          ![](Images/image02.png)
3. Step 3: Model Predictions using SVD Model from (Surprise Package).

---

## Model Training and Predictions
### Logic:
  - Before training some of the work needs to be done in the correected dataset given below:-
      - Step 1: Remove all the users that have rated less movies and also all those movies that has been rated less in numbers.
      - Step 2: Now store all the movie_id indexes in a variable dataset_movie_summary.index and convert the datatype to int
      - Step 3: Create a benchmark.
      - Step 4: Remove all the users that are in-active
      - Step 5: Remove all the customers and movies that are below the benchmark.
      - Step 6: Prepare the dataset for SVD and it takes the matrix as the input so for input, we will convert the dataset into sparse matrix.
      - Step 7: Now Train the model

### Training:
For traning we will be using Surprise Package SVD model.
- **SVD (Singular Value Decomposition)**:
   - A factorization technique that decomposes a matrix (think of a table with rows and columns) into three smaller matrices.
   - These matrices reveal underlying patterns and relationships within the data.
   - SVD is computationally efficient and scalable for large datasets.
   - It can handle sparse data (many missing values) common in recommender systems.
  

### Predictions and Conclusion
 - We will be predicting the recommended movies for  particular user (here used user id is 712664)
 - Recommended movies are shown in ascending as per highest estimate score shown below:-

   ![](Images/image04.png)
 - **Result**
   
      ![](Images/image05.png)
   
 - So we can conclude that the this SVD model works properly on large datasets.
 - We can use this model in OTT platforms and Streaming Services which helps Entertainment industry. Organizations like Netflix, Amazon etc. In analysing user activity pattern's and suggest products that better suit the user needs and choices.
---

  
