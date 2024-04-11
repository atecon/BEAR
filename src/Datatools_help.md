# Datatools Gretl Package Documentation

This package provides a set of tools for data manipulation and analysis in Gretl. Many of the functions are inspired by Python's well-known Pandas library.


## Public Functions

**head()**

```
function void head (const numeric target, const int nrows[1::5])
```

Prints the initial rows of a series, list, or matrix.

*Parameters:*

- `target`: The series, list, or matrix to print.
- `nrows`: The number of rows to print.

**tail()**

```
function void tail (const numeric target, const int nrows[1::5])
```

Prints the last rows of a series, list, or matrix.

*Parameters:*

- `target`: The series, list, or matrix to print.
- `nrows`: The number of rows to print.

**is_str_series()**

```
function scalar is_str_series (const series y)
```

Checks if a given series is string-valued.

*Parameters:*

- `y`: The series to check.

*Returns:*

- `scalar`: Returns TRUE if the series is string-valued, otherwise returns FALSE.

**is_continuous_series()**

```
function scalar is_continuous_series (const series y)
```

Checks if a given series consists of numeric and non-discrete values.

*Parameters:*

- `y`: The series to check.

*Returns:*

- `scalar`: Returns TRUE if the series is numeric and non-discrete, otherwise returns FALSE.

**is_discrete_series()**

```
function scalar is_discrete_series (const series y)
```

Checks if a given series is numeric but characterized as discrete through the `setinfo y --discrete` command.

*Parameters:*

- `y`: The series to check.

*Returns:*

- `scalar`: Returns TRUE if the series is numeric and discrete, otherwise returns FALSE.

**nuniq()**

```
function matrix nuniq (const series y)
```

Counts the number of unique values in a given series. Missing values are ignored and not counted.

*Parameters:*

- `y`: The series to count unique values in.

*Returns:*

- `matrix`: The number of unique values in the series. If `y` is a string series, the distinct string values are additionally printed as row labels.


**nmissing()**

```
function matrix nmissing (const numeric target)
```

Calculates the number of missing values in a given series or list.

*Parameters:*

- `target`: The series or list to calculate the number of missing values for.

*Returns:*

- `matrix`: If the input is a series, returns a matrix with one element - the number of missing values in the series. If the input is a list, returns a matrix with the number of missing values for each series in the list. The row names of the matrix are the variable names from the list, and the column name is "n missing".


**shape()**

```
function matrix shape (const numeric target)
```

Gets the shape of a given series, list, or matrix.

*Parameters:*

- `target`: The series, list, or matrix to get the shape of.

*Returns:*

- `matrix`: A matrix with two elements: the number of rows (or observations) and the number of columns (or elements) in the input.


**dtypes()**

```
function void dtypes (const numeric target)
```

Prints the data types of a given series or list.

*Parameters:*

- `target`: The series or list to print the data types of.


**agg()**

```
function matrix agg (const numeric targets, const numeric groupby, const strings methods)
```

Aggregates data by given methods. This function augments gretl built-in `aggregate()` functions which solely accepts one method.

*Parameters:*

- `targets`: The series or list to aggregate.
- `groupby`: The series or list to group by.
- `methods`: The aggregation methods to use.

The following methods are supported natively by Gretl (See `help aggregate` for more information):

- `sum`: Calculates the sum of the values.
- `sumall`: Calculates the sum of all values, including missing ones.
- `mean`: Calculates the mean (average) of the values.
- `sd`: Calculates the standard deviation of the values.
- `var`: Calculates the variance of the values.
- `sst`: Calculates the sum of squared totals of the values.
- `skewness`: Calculates the skewness of the values.
- `kurtosis`: Calculates the kurtosis of the


*Returns:*

- `matrix`: The aggregated data.



# Changelog

v0.1 (April 2024):
- Initial release

