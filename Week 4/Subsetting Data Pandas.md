# What is Subsetting Data

- choosing specific rows and columns from a dataframe according to labels, indices, and slices
- single column can be selected by using the label of the desired column
	- Ex: using the country dataset assigned to the variable `country` 
		- the Population column can be selected using the `country['Population']` or `country.Population` 
- multiple columns can also be selected by using an array of strings
	- Ex: `country[['Name', 'Population']]` 

#### `iloc(x,y)` Method 

- is used to select an individual element using an index location
	- where `x` is the row and `y` is the column
		- Ex: `country.iloc[0,1]` returns the element in row 0 and column 1
- the colon character `:` is used in slice notation to select multiple rows or columns
	- Ex: `country.iloc[:5,1:3]` returns rows before row 5 and columns 1 thru 2

#### `loc(x.y)` Method 

- can also be used to subset data, but `y`, in this case, is an array of column labels, instead of an integer or a range of integers
	- Ex: both `country.iloc[:7,1:3]` and `country.loc[:6,['Continent','Population']]` give the same results

![[../Images/Images/IMG-20260910184709366.png]]

## Series and dataframes

- `pandas` supports both series and dataframe objects

### What is a Series Object

- a one-dimensional data structure that contains a list with an associate index
	- Ex: `country['Population']` and `country.Population` return a series

### What is a dataframe Object

- a two-dimensional data structure that can contain more that one series
	- Ex: `country[['Population']]` returns a dataframe

| Statement                                         | What it does                                                                  | Result                                       |
| ------------------------------------------------- | ----------------------------------------------------------------------------- | -------------------------------------------- |
| `pd.read_csv('country_subset.csv')`               | Reads a CSV into a DataFrame; the file's first row becomes the column headers | `country`, 239 rows × 3 columns              |
| `country`                                         | Displays the DataFrame as a formatted table, truncated in the middle          | First/last 5 rows + `[239 rows x 3 columns]` |
| `country['Name']`                                 | Selects one column by label — returns a Series                                | Series `Name`, length 239, dtype object      |
| `country[['Name']]`                               | Double brackets return a one-column DataFrame instead of a Series             | 239 rows × 1 column                          |
| `country[['Name', 'Continent']]`                  | A list of labels selects multiple columns. Also returns a DataFrame.          | 239 rows × 2 columns                         |
| `country.iloc[0, 1]`                              | `.iloc` selects by integer position — element at row 0, column 1              | Scalar `'Asia'`                              |
| `country.iloc[0:2, 1]`                            | Rows 0–1 (end-exclusive) at column position 1                                 | Series `Asia, Europe`                        |
| `country.iloc[:7, 1:3]`                           | Rows 0–6 with column positions 1–2                                            | 7 rows × 2 columns                           |
| `country.iloc[10:21, 1:]`                         | Rows 10–20 with everything from column 1 onward                               | 11 rows × 2 columns                          |
| `country.loc[10:20, ['Continent', 'Population']]` | `.loc` selects by label, and slices are end-**inclusive**                     | Same 11 rows × 2 columns as above            |
> [!NOTE]
> - `df['col']` → Series; `df[['col']]` → DataFrame. The extra bracket is the whole difference.
>- `.iloc` uses integer positions and its slices are end-exclusive (standard Python behavior).
>- `.loc` uses labels and its slices are end-**inclusive**, which is why `iloc[10:21]` and `loc[10:20]` return the same rows.
>- Omitting a slice bound means "go to the end" — e.g. `loc[10:20]` in rows or `1:` in columns.

# Subsetting Data Using Comparison and Logical Operators

- when these operators are used only rows for which the expression is true will be returned
	- Ex: `country[country['Population'] > 100000]` will display rows whose `'Population'` column values are greater than 100,000 

![[../Images/Images/IMG-20260910192128976.png]]

![[../Images/Images/IMG-20260910192212422.png]]

| Statement                                                                        | What it does                                                                             | Result                                    |
| -------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ----------------------------------------- |
| `pd.read_csv('country.csv')`                                                     | Reads the CSV into a DataFrame; first row becomes the headers                            | `country`, 6 rows × 8 columns             |
| `country`                                                                        | Displays the DataFrame; with 8 columns, Jupyter wraps output into two column blocks      | Full table, split across two blocks       |
| `country[country['Continent'] == 'South America']`                               | The comparison builds a True/False mask per row; `country[...]` keeps only the True rows | 1 row (Brazil)                            |
| `country[country['Continent'] != 'Asia']`                                        | Same pattern with not-equal; keeps rows where Continent is anything but Asia             | 3 rows (Brazil, Norway, US)               |
| `country[(country['Continent'] == 'Asia') ⏐ (country['Continent'] == 'Europe')]` | Combines two masks with `⏐` (OR); each condition needs its own parentheses               | 4 rows (China, Bangladesh, India, Norway) |
| `country[~(country['Continent'] == 'Asia')]`                                     | `~` negates a boolean mask — works on any mask, including compound ones                  | 3 rows (Brazil, Norway, US)               |
> [!NOTE]
> - Filtering works in two steps: `country['Continent'] == 'Asia'` produces a boolean Series (the "mask"), then `country[mask]` keeps rows where the mask is True.
> - Use `|` for OR and `&` for AND inside a filter — Python's `or`/`and` keywords raise an error because a mask holds many values, not one.
> - Parentheses around each condition are required: comparisons bind tighter than `|` and `&`.
> - `~` inverts any mask, so `~(A | B)` is a clean way to say "neither A nor B."
> - Notice cells 5 and 7 (`!=` vs `~`) return identical results — good sanity check that negation works as expected.


> 