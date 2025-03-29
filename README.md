# Project Title: Querying and Storing Protein Structural Data Using GraphQL and Redis

## Project Overview

This project focuses on retrieving structural and publication data for specific proteins from the RCSB Protein Data Bank (PDB) using a GraphQL API. The retrieved data is then stored in a Redis database, allowing for efficient retrieval and further analysis. The project also includes Python functions to generalize data storage and retrieval for any PDB entry.

### Objectives

  •	Learn how to interact with the `RCSB PDB GraphQL API`.
	•	Extract key protein structural data such as the title, descriptor, and DOI.
	•	Store and retrieve the data using a `Redis database` for efficient access.
	•	Implement reusable functions for querying and storing protein data dynamically.

### Project Steps

#### 1. Querying the RCSB PDB API Using GraphQL

  •	Construct a GraphQL query to fetch structural and publication-related data for selected PDB IDs.
  
  •	Use Python’s requests library to send a GET request to the `RCSB PDB GraphQL API`.
  
  •	Process the API response, extracting important details such as:
  
  •	PDB ID

  •	Structure title
  
  •	Descriptor
    
  •	DOI (if available)

#### 2. Printing the Retrieved Data
  •	Format and print the extracted data in the following structure:
		
		PDB ID: <value>  
		Title: <value>  
		Descriptor: <value>  
		DOI: <value>  
		
#### 3. Storing the Data in Redis
  •	Establish a connection to a Redis database.
  
  •	Store each piece of retrieved data using Redis `key-value` pairs in the format:
		
		<PDB_ID>:title -> Structure Title  
		<PDB_ID>:descriptor -> Structure Descriptor  
		<PDB_ID>:doi -> DOI  
		
  Example:	
  
    6GPB:title -> "Glycogen Phosphorylase Structure"  
		6GPB:descriptor -> "Enzyme involved in glycogen breakdown"  
		6GPB:doi -> "10.1000/journal.example"  
		
#### 4. Retrieving Data from Redis

  Implement a function `get_properties(red, pdb_id)` that:
  
  •	Queries Redis using the `PDB ID`.
  
  •	Prints the retrieved title, descriptor, and DOI.
  
  •	Test the function by retrieving the stored data for PDB ID `8GPB`.

#### 5. Generalizing Data Storage and Retrieval
  Create a function `set_properties(red, pdb_id)` that:

  •	Dynamically fetches data from the API for a given protein ID.
  
  •	Stores the retrieved data in Redis using the same `key-value` format.

  Test the function by:
  
  1.	Storing and retrieving data for PDB ID `7GPB`.

  2.	Storing and retrieving data for PDB ID `4GYD`.
