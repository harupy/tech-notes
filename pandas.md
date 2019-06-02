# pandas

## Select rows containing NaN

`df[df.isnull().any(axis=1)]`

[Python Pandas How to select rows with one or more nulls from a DataFrame without listing columns explicitly? - Stack Overflow](https://stackoverflow.com/questions/14247586/python-pandas-how-to-select-rows-with-one-or-more-nulls-from-a-dataframe-without)

# Check whether all characters in each string are whitespace

`df['col'].str.isspace()`
