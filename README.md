# NoSQL Challenge: UK Food Establishment Analysis

## Project Overview

This project is part of a data analysis challenge focusing on UK food establishments. The goal is to import, update, and analyze data from the UK Food Standards Agency to help the magazine *Eat Safe, Love* identify and evaluate establishments based on food hygiene ratings. The project uses NoSQL (MongoDB) to store and manipulate data and Jupyter Notebooks for running the analysis.

## Project Structure

The project consists of the following key components:

- **`establishments.json`**: The provided dataset containing information about food establishments in the UK.
- **Jupyter Notebooks**:
  - **`NoSQL_setup_starter.ipynb`**: This notebook is used for setting up the MongoDB database, importing data, and performing updates as requested.
  - **`NoSQL_analysis_starter.ipynb`**: This notebook contains exploratory data analysis based on specific queries provided by the magazine editors.

## Technologies Used

- **MongoDB**: NoSQL database used for storing and querying food establishment data.
- **Python**: For scripting and data manipulation.
  - **PyMongo**: Python library for interacting with MongoDB.
  - **Pandas**: Used for data analysis and manipulation in tabular format.
  - **Pretty Print (pprint)**: To format the output of MongoDB queries for better readability.

## Steps Completed

### Part 1: Database and Jupyter Notebook Setup

1. **Imported the dataset** (`establishments.json`) into MongoDB.
    - Database: `uk_food`
    - Collection: `establishments`
2. Verified the database setup by:
    - Listing the available databases and confirming that `uk_food` exists.
    - Listing the collections within `uk_food` and confirming that `establishments` was imported successfully.
    - Displaying a sample document from the `establishments` collection.
3. Created an instance of MongoDB client in the Jupyter notebook and connected it to the database for further operations.

### Part 2: Database Update

1. **Added a new restaurant** to the `establishments` collection as per the editor's request.
    - Business name: "Penang Flavours" (with pending rating)
2. **Updated the new restaurant** with the appropriate `BusinessTypeID` for "Restaurant/Cafe/Canteen".
3. **Removed establishments** located in the Dover Local Authority from the collection, as they were not of interest to the magazine.
4. **Data Cleaning**:
    - Converted `latitude` and `longitude` values from strings to decimal numbers.
    - Converted `RatingValue` to integer where appropriate, handling non-numeric values by setting them to null.

### Part 3: Exploratory Data Analysis

1. **Identified establishments with a hygiene score of 20**.
2. **Filtered establishments in London with a RatingValue greater than or equal to 4**.
3. **Found the top 5 establishments with a RatingValue of 5**, sorted by lowest hygiene score, nearest to the new "Penang Flavours" restaurant.
4. **Aggregated establishments with a hygiene score of 0**, grouped by Local Authority, and sorted by the number of establishments in descending order.

## Key Queries Answered

- Which establishments have a hygiene score equal to 20?
- Which establishments in London have a RatingValue greater than or equal to 4?
- What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to "Penang Flavours"?
- How many establishments in each Local Authority area have a hygiene score of 0? (Top 10 authorities listed)

## Results Summary

- The data exploration revealed multiple insights, such as high concentrations of establishments with poor hygiene in specific areas and a list of top-rated establishments with excellent ratings close to the new restaurant.
- The magazine can use these insights to guide their future articles and restaurant reviews.

## How to Run the Project

1. **Clone the repository** from GitHub.
2. **Install MongoDB** and make sure it's running.
3. **Import the `establishments.json` data** into MongoDB using the following command:

    ```bash
    mongoimport --db uk_food --collection establishments --file Resources/establishments.json --jsonArray
    ```

4. Open and run the Jupyter Notebooks in order:
   - `NoSQL_setup_starter.ipynb`
   - `NoSQL_analysis_starter.ipynb`

## Conclusion

This project demonstrates how to manage and analyze NoSQL data in MongoDB, leveraging Python and PyMongo for effective data manipulation and exploration. The insights gained will assist *Eat Safe, Love* in evaluating food establishments across the UK.
