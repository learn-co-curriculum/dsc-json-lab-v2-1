# JSON - Lab

## Introduction

In this lab, you'll practice navigating JSON data structures.

## Objectives

You will be able to:

* Practice using Python to load and parse JSON documents

## Your Task: Find the Total Payments for Each Candidate

We will be using the same dataset, `nyc_2001_campaign_finance.json`. The description of this file is:

> A listing of public funds payments for candidates for City office during the 2001 election cycle

For added context, the Ciy of New York provides matching funds for eligible contributions made to candidates, using various ratios depending on the contribution amount ([more details here](https://en.wikipedia.org/wiki/New_York_City_Campaign_Finance_Board#The_Campaign_Finance_Program)). So these are not the complete values of all funds raised by these candidates, they are the amounts matched by the city. For that reason we expect that some of the values will be identical for different candidates.

The dataset is separated into `meta`, which contains metadata, and `data`, which contains the actual campaign finance records. You will need to use the information in `meta` to understand how to interpret the information in `data`.

Your goal is to create a list of tuples, where the first value in each tuple is the name of a candidate in the 2001 election, and the second value is the total payments they received. The structure should look like this:

```python
[
    ("John Smith", 62184.00),
    ("Jane Doe", 133146.00),
    ...
]
```

The list should contain 284 tuples, since there were 284 candidates.

## Open the Dataset

Import the `json` module, open the `nyc_2001_campaign_finance.json` file using the built-in Python `open` function, and load all of the data from the file into a Python object using `json.load`.

Assign the result of `json.load` to the variable name `data`.


```python
# Your code here
```

Recall the overall structure of this dataset:


```python
# Run this cell without changes

print(f"The overall data type is {type(data)}")
print(f"The keys are {list(data.keys())}")
print()
print("The value associated with the 'meta' key has metadata, including all of these attributes:")
print(list(data['meta']['view'].keys()))
print()
print(f"The value associated with the 'data' key is a list of {len(data['data'])} records")
```

## Find the Column Names

We know that each record in the data list looks something like this:


```python
# Run this cell without changes
data['data'][1]
```

We could probably guess which of those values is the candidate name, but it's unclear which value is the total payments received. To get that information, we need to look at the metadata.

Investigate the value of `data['meta']['view']['columns']`.

Let `data['meta']['view']['columns']` be called `column_data`. Verify that `column_data` results in a list.


```python
# Your code here (create more cells as needed)
column_data = None

```

Now look at the first few entries of `column_data`.

The result should look something like this:

```python
[
    "sid",
    "id",
    "position",
    ...
]
```


```python
# Your code here (create more cells as needed)

# With a list, it's often useful to look at the
# first entry, or first few entries
```

`column_data` currently contains significantly more information than we need. Extract just the values associated with the `name` keys using list comprehension, so we have a list of the column names.

Now name this variable `column_names`.


```python
# Your code here (create more cells as needed)

column_names = None
```


```python
# Run this cell without changes

# There should be 19 names
assert len(column_names) == 19
# CANDNAME and TOTALPAY should be in there
assert "CANDNAME" in column_names and "TOTALPAY" in column_names
```

Now we know what each of the columns represents.

The columns we are looking for are called `CANDNAME` and `TOTALPAY`. Now that we have this list, we should be able to figure out which of the values in each record lines up with those column names.

## Loop Over the Records to Find the Names and Payments

The data records are contained in `data['data']`. 

To loop over the records to find the names and payments, first we need to determine the indices of the candidate names and the total payments.

Let `name_index` be the column names of `CANDNAME` and `total_payments_index` be the column names of `TOTALPAY`. After correctly defining `name_index` and `total_payments_index`, print their respective indices.




```python
# Your code here (create more cells as needed)

# In theory we could just look at the list and
# count by hand to figure out the index of these
# strings, but Python can do it for us

name_index = None
total_payments_index = None
```

Now loop over the records in `data['data']` and extract the name from `name_index` and total payment from `total_payments_index`. Make sure you convert the total payment to a float, then make a tuple representing that candidate. Append the tuple to an overall list of results called `candidate_total_payments`.

Recall that the first (`0`-th) one is more of a header and should be skipped over.

To verify that your loop worked, print the first five and the last five records.


```python
# Your code here (create more cells as needed)

candidate_total_payments = []

# Loop over records starting at index 1 to skip header



# Print the first five and last five

```


```python
# Run this cell without changes

# There should be 284 records
assert len(candidate_total_payments) == 284

# Each record should contain a tuple
assert type(candidate_total_payments[0]) == tuple

# That tuple should contain a string and a number
assert len(candidate_total_payments[0]) == 2
assert type(candidate_total_payments[0][0]) == str
assert type(candidate_total_payments[0][1]) == float
```

Now that we have this result, we can answer questions like: *which candidates received the most total payments from the city*?


```python
# Run this cell without changes

# Print the top 10 candidates by total payments
sorted(candidate_total_payments, key=lambda x: x[1], reverse=True)[:10]
```

Since you found all of the column names, it is also possible to display all of the data in a nice tabular format using pandas. That code would look like this:


```python
# Run this cell without changes

import pandas as pd

pd.DataFrame(data=data['data'][1:], columns=column_names)
```

## Summary

You've started exploring some more JSON data structures used for the web and got to practice data munging and exploring.
