# DataCleaningUsingFUZZY
A project for cleaning Australian state names using Fuzzy Matching in Python.

## Overview
This project focuses on data cleaning for a dataset containing state names. The primary objective is to clean the State column, which may contain inconsistencies such as abbreviations, typos, or different formats. The dataset used for concept building contains Australian state names.

In this project, we apply various techniques including:
- Exact matching
- Fuzzy matching
- Regular expressions (regex)
- Standardization of state names

This ensures the state names are uniform, which is crucial for further data analysis, reporting, and decision-making.

## Dataset
The dataset consists of various records, each representing an entity or observation associated with a specific state in Australia. The State column may contain:

Full state names (e.g., "New South Wales")

Abbreviations (e.g., "NSW")

Misspellings or variations (e.g., "Qld", "Queenslad", "Westn Austra")

### Example of the raw data (before cleaning):
ID	State
1	NSW
2	Queensland
3	Westn Austra
4	Sou Aus
5	Tas
6	As Cap

## Objectives
- Standardize all state names to a consistent format.
- Handle abbreviations, misspellings, and partial names.
- Clean and preprocess state names to ensure accuracy for analysis or visualization.

## Approach
The data cleaning process was carried out in the following steps:

### Preprocessing:
- Removed special characters (e.g., extra spaces, punctuation).
- Converted all text to lowercase for uniformity.

### Exact Matching:
- Created a dictionary to map abbreviations and variations of state names to their correct counterparts.
- Used exact string matching for names that already existed in the dictionary.

### Prefix Matching:
- Used common prefixes to match partial state names (e.g., "So" matched to "South Australia", "Tas" matched to "Tasmania").

### Fuzzy Matching:
- Applied fuzzy matching techniques to catch misspellings and typos.
- Used the RapidFuzz library to find the closest matching state names when exact matches failed.

### Final Validation:
- Checked that all state names were successfully mapped to their correct counterparts from the dictionary or fuzzy matching.
- Marked invalid names (those that couldn't be mapped) for further inspection or correction.

### Example of the cleaned data (after cleaning):
ID	State
1	New South Wales
2	Queensland
3	Western Australia
4	South Australia
5	Tasmania
6	Australian Capital Territory

## Technologies Used
- Python: The data cleaning was done using Python, specifically the pandas library for data manipulation.

- RapidFuzz: A fuzzy matching library for handling partial matches, misspellings, and variations.

- Regular Expressions (regex): Used for text cleaning, such as removing non-alphanumeric characters.

- pandas: To load and manipulate the dataset (e.g., reading from Excel, applying transformations, saving cleaned data).
