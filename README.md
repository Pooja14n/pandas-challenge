# pandas-challenge

# PyCitySchools
![education](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/7f356b59-c83c-4f37-8d4c-05bd195051b3)

For a city's school district, the school board and mayor need help with strategic decisions regarding future school budgets and priorities. As a first task, the district-wide standardized test results have to be analyzed. Access will be given to every student's math and reading scores, as well as various information on the schools they attend. The task is to aggregate the data to showcase obvious trends in school performance.

# Requirements
Pandas and Jupyter Notebook to create a report that includes data as elaborated below. And, a report that summarizes the analysis and draws two correct conclusions or comparisons from the calculations based on the 2 datasets proveded.

# District Summary
Perform the necessary calculations and then create a high-level snapshot of the district's key metrics in a DataFrame.
Include the following:
  1. Total number of unique schools
  2. Total students
  3. Total budget
  4. Average math score
  5. Average reading score
  6. % passing math (the percentage of students who passed math)
  7. % passing reading (the percentage of students who passed reading)
  8. % overall passing (the percentage of students who passed math AND reading)

![2](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/c4623e92-e84c-47d4-8579-98f49df4390c)

# School Summary
Perform the necessary calculations and then create a DataFrame that summarizes key metrics about each school.
Include the following:
  1. School name
  2. School type
  3. Total students
  4. Total school budget
  5. Per student budget
  6. Average math score
  7. Average reading score
  8. % passing math (the percentage of students who passed math)
  9. % passing reading (the percentage of students who passed reading)
  10. % overall passing (the percentage of students who passed math AND reading)

![3](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/2ff9539d-1d5a-477e-8a85-2dbc30745946)


# Highest-Performing Schools (by % Overall Passing)
Sort the schools by % Overall Passing in descending order and display the top 5 rows.

Save the results in a DataFrame called "top_schools".

![4](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/6542a362-7a1a-401a-8340-489574ae7f11)


# Lowest-Performing Schools (by % Overall Passing)
Sort the schools by % Overall Passing in ascending order and display the top 5 rows.

Save the results in a DataFrame called "bottom_schools".

![5](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/baa6c0db-7eb0-4f35-8c33-0d6f5d4ffca0)


# Math Scores by Grade
Perform the necessary calculations to create a DataFrame that lists the average math score for students of each grade level (9th, 10th, 11th, 12th) at each school.

![6](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/4e305802-6e74-41aa-856c-18cdbe161a2d)


# Reading Scores by Grade
Create a DataFrame that lists the average reading score for students of each grade level (9th, 10th, 11th, 12th) at each school.

![7](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/ad5bce95-35ff-4353-a7be-61ca5dcc5663)


# Scores by School Spending
Create a table that breaks down school performance based on average spending ranges (per student).

Use the code provided below to create four bins with reasonable cutoff values to group school spending.

spending_bins = [0, 585, 630, 645, 680]
labels = ["<$585", "$585-630", "$630-645", "$645-680"]
Use pd.cut to categorize spending based on the bins.

![8](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/fc4d6730-09bc-422d-a347-b581011d5941)

Use the following code to then calculate mean scores per spending range.

spending_math_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Math Score"].mean()
spending_reading_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Reading Score"].mean()
spending_passing_math = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Math"].mean()
spending_passing_reading = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Reading"].mean()
overall_passing_spending = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Overall Passing"].mean()
Use the scores above to create a DataFrame called spending_summary.

Include the following metrics in the table:
  1. Average math score
  2. Average reading score
  3. % passing math (the percentage of students who passed math)
  4. % passing reading (the percentage of students who passed reading)
  5. % overall passing (the percentage of students who passed math AND reading)

![9](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/5295dfd1-140c-48f6-8e5d-d9b618c13ca3)


# Scores by School Size
Use the following code to bin the per_school_summary.

size_bins = [0, 1000, 2000, 5000]
labels = ["Small (<1000)", "Medium (1000-2000)", "Large (2000-5000)"]
Use pd.cut on the "Total Students" column of the per_school_summary DataFrame.

![10](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/27d8e988-a976-416d-b1bb-ebe247415300)

Create a DataFrame called size_summary that breaks down school performance based on school size (small, medium, or large).

![11](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/3bef15b7-b878-422e-9f02-cf00e07fff2e)


# Scores by School Type
Use the per_school_summary DataFrame from the previous step to create a new DataFrame called type_summary.

This new DataFrame should show school performance based on the "School Type".

![12](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/87b6be6a-07c5-435b-8d82-1d4052ace4c3)


# Note
Initial steps carried out prior to coding are:
  1. Dependencies and Setup
      `import pandas as pd`
      `from pathlib import Path`
  2. File to Load 
      school_data_to_load = Path("Resources/schools_complete.csv")
      student_data_to_load = Path("Resources/students_complete.csv")
  3. Read School and Student Data File and store into Pandas DataFrames
      school_data = pd.read_csv(school_data_to_load)
      student_data = pd.read_csv(student_data_to_load)
  4. Combine the data into a single dataset.  
      school_data_complete = pd.merge(student_data, school_data, how="left", on=["school_name", "school_name"])
      school_data_complete.head()

![1](https://github.com/Pooja14n/matplotlib-challenge/assets/144713762/c9f5c3c8-fff7-4a9a-a11d-07e16111ecca)

# References
Referred to various class activity exercises, and websites for: Pandas Documentation, Stack Overflow, Geeksforgeeks, and Datatofish.

# Files submitted including this README File
1. Folder -> PyCitySchools
2. Resources folder -> 2 Datasets provded for the analysis:
   a. schools_complete.csv
   b. students_complete.csv
3. Jupyter Notebook that contains the main script to run for analysis and the report that includes a written description of at least two observable trends based on the data -> PyCitySchools_analysis.ipynb
   
