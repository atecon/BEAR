# PandasPort Gretl Package Documentation

PandasPort is a collection of functions that are inspired by Python's well-known Pandas library. The package aims to provide a familiar and intuitive environment for users transitioning from Pandas to the Gretl software for data analysis and econometrics.

PandasPort includes a comprehensive set of functions that mimic the functionality of popular Pandas methods. This package serves as a bridge, enabling a smooth migration path while taking advantage of Gretl's powerful econometric analysis capabilities.


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

Checks if a given series is string-valued. It's a short-cut for `nelem(strvals(y))`.

*Parameters:*

- `y`: The series to check.

*Returns:*

- `scalar`: Returns TRUE if the series is string-valued, otherwise returns FALSE.


**value_counts()**


```
function matrix value_counts (const numeric y)
```

Counts the occurrence of each unique value in a series or matrix (column vector). This corresponds to the frequency of each distinct observation.

*Parameters:*

- `y`: The series or matrix to count unique values in. If a matrix is provided, it must be a column vector.
- `normalize` (optional, default is FALSE): If TRUE, the output will show the relative frequencies of the values instead of their counts.

*Returns:*

- `matrix`: A matrix with the counts or relative frequencies of each unique value in the input. The row names of the matrix are the unique values from the input, and the column name is the name of the input variable.

If 'normalize' is TRUE, the column name is appended with "rel.freq.", otherwise it is appended with "count".

**Note**: For both series and matrix inputs, eventual missing values are not ignored when computing relative frequencies.


```
function matrix nuniq (const series y)
```

Counts the number of distinct values in a given series. Missing values are ignored and not counted.
Suppose a series consists of booleans (0 and 1), then the number of unique values is 2.

*Parameters:*

- `y`: The series to count unique values in.

*Returns:*

- `matrix`: The number of unique values in the series. If `y` is a string series, the distinct string values are additionally printed as row labels.


**nmissing()**

```
function matrix nmissing (const numeric target)
```

Calculates the number of missing values in a given series, list or matrix.

*Parameters:*

- `target`: The series, list or matrix to calculate the number of missing values for.

*Returns:*

- `matrix`: If the input is a series, returns a matrix with one element - the number of missing values in the series. If the input is a list or matrix, returns a matrix with the number of missing values for each series/ column. The row names of the matrix are the variable names from the list/ matrix, and the column name is "n missing".


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

Prints the data types of a given series or list. The datatype can be:

- "string" for a string-values series
- "discrete" for discrete series
- "continuous" for the standard case

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

