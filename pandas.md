---
id: pandas
aliases:
  - Pandas
tags: []
---

# Pandas
Pandas is good to use with 2d data rows & columns

```python
import pandas as pd
```


## Dataframe

  Dataframe is a 2D labeled data structure like spreadsheet or csv file

```python
    df = pd.read_csv('file.csv') 
    df = pd.read_excel('excel_file.xlsx')
    df = pd.DataFrame(dictionary_data)
    -> "When dataframe is created it will automatically give indices(row num) starting from 0"
```

```python
    df.head() -> "Show first 5 rows to undestand the structure"
    df.tail() -> "Last 5 rows"
    df.info() -> "General info about dataframe"
    df.columns -> "Return a list of colum names"
```

```python
    df['column_name'] -> "Return row values for the column as a list"
    df.[['column1', 'column2']] -> "Return values for 2 columes"

    df.iloc['row index'] -> "Return value for the row"
    df.iloc['row_indec']['colum_name']
```

```python
    df[(df['column_name'] == 'value') & (df['column_name2'] == 'value')] -> "Filter rows based on the colum value with and condition"
    df[(df['column_name'] == 'value') | (df['column_name2'] == 'value2')] -> "Filter rows based on the colum value with or condition"
    df[(df['column_name'] >= 'value') ] 
    df[(df['column_name'].str.startswith('')) ] 
    df[(df['column_name'].isin([list of values])) ] "Reverse condition by using ~" 

```

```python
    df.drop('row_index') 
    df.dropna() -> 'Remove N/A values'
    df.fillna({'column_name': 'value'}, inplace=true) -> 'Fill Na values with the given value'
```
