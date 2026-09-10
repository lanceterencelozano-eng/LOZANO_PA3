# Programming Assignment 3
#### Lance Terence A. Lozano | 2ECE-C

## Objectives
1. load a CSV dataset into a Pandas DataFrame;
2. select rows and columns using positional and label-based indexing;
3. filter records using conditions on a DataFrame column; and
4. extract a well-defined subset of data without changing the source data.

To access Pandas library, the import convention must be used:

`import pandas as pd`
```python
cars = pd.read_csv('cars.csv')
cars
```
This code reads the cars.csv file into a Pandas DataFrame named cars and displays its contents in the notebook.

## A. Positional and Label-Based Slicing
a.
```python
cars.shape
```
```python
cars.columns
```
This code retrieves and displays the dimensions (rows and columns) alongside the complete list of column names for the `cars` DataFrame.

b.
```python
cars_6_to_10 = cars.iloc[6:11]
cars_6_to_10
```
This code extracts positional rows from index 6 through 10 using `.iloc[6:11]`, assigns the result to `cars_6_to_10`, and displays the DataFrame.

c.
```python
cars_6_to_10[['Model','mpg','cyl','hp','gear']]
```
This code selects and displays only the `'Model'`, `'mpg'`, `'cyl'`, `'hp'`, and `'gear'` columns from the `cars_6_to_10` subset.

## B. Model Lookup
a.
```python
toyota = cars.loc[cars['Model'] == 'Toyota Corolla']
toyota
```
This code filters the `cars` DataFrame for the `'Toyota Corolla'` model, assigns the matching row to `toyota`, and displays it.

b.
```python
pontiac = cars.loc[cars['Model']=='Pontiac Firebird', ['Model','mpg','hp','wt']]
pontiac
```
This code extracts the `'Model'`, `'mpg'`, `'hp'`, and `'wt'` columns for the `'Pontiac Firebird'` model, assigns the result to `pontiac`, and displays it.

## C. Multi-Model Subsetting
```python
selected_cars = cars.loc[(cars['Model']=='Datsun 710') | (cars['Model']=='Lotus Europa') | (cars['Model']=='Ferrari Dino'), ['Model','mpg','cyl','hp','gear']]
selected_cars
```
This code uses boolean OR `|` logic to filter `cars` for three specific models (`'Datsun 710'`, `'Lotus Europa'`, and `'Ferrari Dino'`) with selected columns, assigns the result to `selected_cars`, and displays it.

```python
selected_cars.shape
```
This code displays the row and column dimensions of the `selected_cars` DataFrame.

## README File Version History
September 10,2026 - Initial README output uploaded
