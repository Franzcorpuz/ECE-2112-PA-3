# ECE-2112-PA-3
Made by: Franz Justin M. Corpuz | 2ECE-D

The content of this repository contains the Programming Assignment 3 for our course ECE2112 Advanced Computer Programming. This assignment focuses on fundamental techniques of Python's Pandas Library. This assignment would help with importing CSV files into Pandas DataFrames and selecting specific rows and columns using both positional and label-based indexing methods. Furthermore, this would also teach how to apply conditional logic to filter column values and extract precise data subsets while ensuring the original source data remains unmodified.

# Importation of the Pandas Library
Before the coding for this Programming Assignment starts, the Pandas library must be imported into the notebook to be able to use most of the functions that are needed to fulfill the requirements in this assignment.

To import the Pandas Library it must be activated using this syntax:
```python
import pandas as pd
```
"pd" was used as a variable for pandas to make it easier to call, but "import pandas" would also work.

# CARS Table
To fulfill all the functions and operations that will be used, this table is needed, since everything revolves around it (see [View cars.csv](cars.csv).
For Python to read the .csv file, it needs the Pandas Library and this syntax:
```python
cars = pd.read_csv('cars.csv')
```

# A. POSITIONAL AND LABEL-BASED SLICING
**Objective:** To display the shape and complete list of column names of cars, use positional slicing to create cars_6_to_10 containing rows 6 through 10, and display only the Model, mpg, cyl, hp, and gear columns in that specified order.

To solve the Positional and Label-Based Slicing the following functions and operators were used:
```python
cars = pd.read_csv('cars.csv')
cars

carshape = cars.shape
print("Shape of the list: ", carshape)
```
cars = pd.read_csv('cars.csv') was used to read the .csv file containing the list of cars, which will be named cars. The list can also be displayed by just inputting cars in the cell. To obtain the shape of the list, the syntax carshape = cars.shape was used to display the list's dimensions.

```python
cars_6_to_10 = cars.iloc[6:11]
```
To locate the information about the cars from rows 6-10 the syntax cars_6_to_10 = cars.iloc[6:11] was used to isolate and create a new list where the cars from 6-10 are the only content.

```python
cars_6_to_10selcol = cars_6_to_10.loc[:,['Model','mpg','cyl','hp','gear']]
```
cars_6_to_10.loc[:,['Model','mpg','cyl','hp','gear']] was the syntax used to locate the cars from rows 6-10 then filter the columns to only display the selected columns such as the 'Model','mpg','cyl','hp','gear' the order that the list was written is also the order it will be displayed.

# B. MODEL LOOKUP
**Objective:** To use Boolean indexing on the Model column to display the complete row for Toyota Corolla, and to filter and display only the Model, mpg, hp, and wt columns for Pontiac Firebird.

To solve the Model Lookup problem the following functions and operators were used:
```python
Toycor = cars.loc[cars['Model'] == 'Toyota Corolla']
Toycor
```
This syntax was used to easily locate the Toyota Corolla model. Boolean indexing was used with the "==" operator to check whether each model in the list equals the specified model, such as the Toyota Corolla. Then the call Toycor was just used to display the model's row.

```python
Pontfi = cars.loc[cars['Model'] == 'Pontiac Firebird']

Pontfisel = Pontfi.loc[:,['Model','mpg','hp','wt']]
```
Similar to the first part of this problem, I used Boolean indexing to find the car model Pontiac Firebird, which I named Pontfi. However, to fulfill the task in this part, I need to select the columns that need to be displayed, such as the Model, mpg, hp, and wt, which I syntaxed using Pontfisel = Pontfi.loc[:,['Model','mpg','hp','wt']].

# C. MULTI-MODEL SUBSETTING
**Objective:** To create a DataFrame named selected_cars containing records for Datsun 710, Lotus Europa, and Ferrari Dino by selecting rows based on their model values rather than row numbers, retaining only the Model, mpg, cyl, hp, and gear columns, and displaying selected_cars along with its shape.

To solve the Multi-Model Subsetting problem the following functions and operatosr were used:
```python
a = cars.loc[cars['Model'] == 'Datsun 710',['Model','mpg','cyl','hp','gear']]
b = cars.loc[cars['Model'] == 'Lotus Europa',['Model','mpg','cyl','hp','gear']]
c = cars.loc[cars['Model'] == 'Ferrari Dino',['Model','mpg','cyl','hp','gear']]
```
 cars.loc[cars['Model'] == 'Model Name',['Model','mpg','cyl','hp','gear']] was the syntax used to make the two step process in Problem B earlier this syntax just made the locating of the car through the Model and column and the selecting of the columns to be displayed in just one line of syntax. This was used three times to obtain the information of the 3 cars that is needed. 

 ```python
selected_cars = pd.concat([a ,b ,c])
```
Since the information for the three cars was obtained one by one, the pd.concat([a, b, c]) syntax was used to concatenate the three cars and create a list containing only the model, mpg, cyl, hp, and gear. 





README File Version History

September 7, 2026 - Created the Repository

September 7, 2026 - Uploaded the finished code

September 9, 2026 - Started writing the README file

September 9, 2026 - Finished the Repository
