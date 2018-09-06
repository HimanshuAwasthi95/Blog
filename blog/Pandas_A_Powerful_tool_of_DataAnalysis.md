# Pandas - A Powerful tool of Data Science

## Data Science : 

Now a days every one talking about **data** whether it is related to personal life , business life or in Technology. We all heard beautiful word by W. Edwards Deming -

```
“Without data you’re just a person with an opinion.”
```
This is quote for all of us because It force us to find relevent and useful information from huge number of Data. No one listen or follow our opinion if we don't have facts and data to show. 

Data Science is not about mathematics(statistics) , Not about engineering capabilities , Not about business analyst but its all about the combination of each and every thing like statistics, computer science, Business analysis. Data Science includes working with algorithms , Extract knowledge and data from so many resources whether it is structured or unstructured.

```
Data Science is just a way to take Data driven Decisions
```
Data Science is very helpful when we talk about predictive analysis like weather forecasting, Stock Market behaviour and a lot of thing which impact our life directely.

## Why Pandas : 

Why ??????? Pandas ........

```
Pandas Because its open source python library.
```

Pandas is a [Numfocus](https://www.numfocus.org/open-source-projects.html) Sponsored BSD-licensed [Python](https://www.python.org/) library which allows you do fast data analysis as well as data cleaning. Pandas is typically the intermediate tool used for data exploration and cleaning, data modeling and predicting.

The power you have when you use pandas is that it is a Tool which gives you freedom to play with any structure of data like CSV and text files, Microsoft Excel, SQL databases, and the fast HDF5 format or even a webpage.

## Lets Dive into Pandas:

### Installing Pandas:

**Install pandas using conda(Use [Anaconda](https://www.anaconda.com/))**

```
conda install pandas
```
If you do not have Anaconda on your computer,

**Install pandas using pip**

```
pip install pandas
```

### Data Structure using *Pandas*:

There are three types of Data Structure in Pandas:
  * Series
  * Data Frame
  * Panel

#### Series: 
Series is a one-dimensional labeled array capable of holding data in integer, string, float, python objects type etc. The axis labeles are referred to as the *index* . A Series is similar to a list or an array in Python. How a Series works ?

you just need to import the pandas into your Python program and you are ready to go:

```
impord pandas as pd
```
The basic method to create a Series is to call:
```
First_series = pd.Series(data, index=index)
```

**Create a Series from ndarray:** If data is an ndarray, index must be the same length as data.  If no index is passed, default will be created having values [0, ..., len(data) - 1].

```
In [1]: import pandas as pd

In [2]: import numpy as np

In [3]: data = np.array(['A' , 'B', 'C', 'D', 'E'])

In [4]: series_from_ndarray = pd.Series(data)

In [5]: print (series_from_ndarray)
0    A
1    B
2    C
3    D
4    E
dtype: object
```
We did not pass any index, so by default, it assigned the indexes ranging from 0 to len(data)-1, i.e., 0 to 3.

**Series from Dictionary:** Series can be created by Dictionary. When the data is a dict, and an index is not passed, the Series index will be ordered by the dict’s insertion order.

```
In [7]: dictionary = {'Zeomega': 100 , 'Zeolearn' : 200 , 'Medium':300, 'Tutoria
   ...: lPoints': 400}

In [8]: pd.Series(dictionary)
Out[8]: 
Medium            300
TutorialPoints    400
Zeolearn          200
Zeomega           100
dtype: int64
```

#### DataFrame: 
A Data frame is a two-dimensional data structure with columns of potentially different types. Data is in the form of tabular form like row and column. 
It is widely used pandas object. DataFrame accepts many different kinds of input:

        * Dict of 1D ndarrays, lists, dicts, or Series
        * 2-D numpy.ndarray
        * Structured or record ndarray
        * A Series
        * Another DataFrame
        



