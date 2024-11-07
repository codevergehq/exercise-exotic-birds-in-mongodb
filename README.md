# Exercise: Exotic Birds in MongoDB

## Learning Goals

Upon completing this exercise, you will be able to:

- Execute basic MongoDB queries to retrieve specific data from a MongoDB database
- Apply comparison operators to filter data based on numerical values
- Implement array operators to search within array fields
- Utilize element operators to check field existence and types
- Create projections to display selected fields in query results
- Construct complex queries combining multiple conditions
- Import and manage JSON data in MongoDB Compass
- Test and validate query results using MongoDB Compass

## Introduction

Welcome to the Exotic Birds Database Lab! 🦅 

In this exercise, you'll work with a dataset containing information about various exotic bird species from around the world. 

You'll practice performing different types of queries using MongoDB Compass, applying what you've learned about MongoDB's query operators, projections, and data manipulation techniques. 🦉

## Getting Started

1. [Fork this repository](https://github.com/codevergehq/exercise-exotic-birds-in-mongodb)
2. Clone the repository to your computer
3. Open the repository in VS Code
4. Follow instructions

## Setup in MongoDB Compass

1. After forking the repository and cloning it locally, navigate to the data folder:

```bash
cd mongodb-exotic-birds
cd data
```


Inside the `data` folder, you’ll find the `exotic-birds.json` file which contains a dataset of 50 exotic bird species.

2. Once you’re in the `data` folder, import the exotic birds collection with the following command:

```bash
mongoimport --db exoticBirds --collection birds --jsonArray --file exotic-birds.json
```

3. Open MongoDB Compass and verify that you can see your `exoticBirds` database. It should contain the `birds` collection with 50 exotic bird entries.


## Instructions

Your task is to create queries that solve the instructions below. You can work locally with your exotic-birds dataset in MongoDB Compass to build and execute these queries.

After you've obtained the desired result, copy the corresponding query into your `index.js` file under each question. At the end of this exercise, you'll be asked to commit your work and create a pull request in GitHub so that we can check your work. 

Have fun exploring the exotic birds dataset! 🦜🙂

### Basic Queries

1. Find all birds that belong to the Psittacidae family.
2. Find all birds that have a lifespan greater than 40 years.
3. Find all birds that can talk and sort them by their scientific name.

### Comparison Operators

4. Find all birds with a wingspan between 80 and 120 centimeters.
5. Find all birds that weigh less than 500 grams or more than 2000 grams.

### Array Operators

6. Find all birds that have both "Seeds" and "Fruits" in their diet.
7. Find all birds that live in either "Rainforest" or "Tropical woodland" habitats.

### Element Operators

8. Find all birds where the conservation population is not specified.
9. Find all birds where the lastSeen field is of type "date".

### Projections

10. Display only the common name and scientific name of all endangered birds.

### Complex Queries

11. Find all birds from South America that are endangered and have a population less than 10000.
12. Find all birds that have "Deforestation" listed as a threat and sort them by population in ascending order.

### Update Operations

13. Update the conservation status of all birds with a population less than 5000 to "Critically Endangered".
14. Add "Climate Change" to the threats array for all birds from tropical habitats.

### Advanced Aggregation

15. Find the average lifespan of birds for each family.

### Bonus Challenges

16. Find all birds that have been seen in the last 6 months and are endangered.
17. Calculate the average wingspan for each continent.
18. Find the bird families with the most endangered species.


## Submission

Add the corresponding query for each task to the `index.js` file.
When you're ready, run the following commands:

```bash
git add .
git commit -m "done"
git push -u origin main
```


## Frequently Asked Questions (FAQs)

<details>
<summary>How do I know if my query is correct?</summary>
Test your query in MongoDB Compass first. 

If it returns the expected results, copy it to your `index.js` file. The query should match the requirements of each task and return relevant data about the birds.
</details>

<details>
<summary>What if my mongoimport command fails?</summary>
Common issues include:

- Being in the wrong directory (make sure you're in the `data` folder)
- Incorrect file name (check that it's exactly `exotic-birds.json`)
- JSON format issues (ensure the file starts with [ and ends with ])
- MongoDB not running (ensure your MongoDB service is active)
</details>

<details>
<summary>How do I format my queries in the `index.js` file?</summary>
Place your query within the corresponding comment block. For example:

```javascript
/* 1. Find all birds that belong to the Psittacidae family
   Your query: 
       
{ "family": "Psittacidae" }

*/
```
</details>

<details>
<summary>Should I include the projection/sort/limit in my query?</summary>
Yes, if the task requires specific fields or ordering, include all relevant query components. 
For example:

```
/* Display only common name and scientific name of endangered birds */
```

{
  "query": { "isEndangered": true },
  "projection": { "commonName": 1, "scientificName": 1, "_id": 0 }
}
</details>

<details>
<summary>What if my query returns no results?</summary>
Double-check:

	•	Field names (they are case-sensitive)
	•	Value types (strings in quotes, numbers without quotes)
	•	Array operators syntax (correct use of $in, $all, etc.)
	•	Data exists in your database (verify successful import)
</details>

<details>
<summary>How can I test complex queries?</summary>
Break down complex queries into smaller parts and test each part separately in MongoDB Compass before combining them. Use the Compass interface to build and validate your queries before adding them to your solution.
</details>

<details>
<summary>What's the difference between `$in` and `$all` operators?</summary>
-  `$in` matches ANY of the values in an array
- `$all` matches ALL of the values in an array

Choose based on whether you need to match any or all conditions.
</details>