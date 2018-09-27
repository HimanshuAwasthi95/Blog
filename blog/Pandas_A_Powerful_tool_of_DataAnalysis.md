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
        * Another DataFrame
 
**Create an Empty DataFrame:** 
```
#import the pandas library and aliasing as pd
import pandas as pd
df = pd.DataFrame()
print df
```
Output:
```
Empty DataFrame
Columns: []
Index: []
```

#### Panel:
A **Panel** is the 3 D Container of Data.
Represented as **pandas.Panel()**
A Panel can be created using the following constructor:
```
class pandas.Panel(data=None, items=None, major_axis=None, minor_axis=None, copy=False, dtype=None)
```
```
#creating an empty panel
import pandas as pd
import numpy as np

data = {'Item1' : pd.DataFrame(np.random.randn(4, 3)), 
        'Item2' : pd.DataFrame(np.random.randn(4, 2))}
p = pd.Panel(data)
print p
```
Output :
```
<class 'pandas.core.panel.Panel'>
Dimensions: 2 (items) x 4 (major_axis) x 5 (minor_axis)
Items axis: 0 to 1
Major_axis axis: 0 to 3
Minor_axis axis: 0 to 4
```

### Perform Basic operation of Pandas:

#### Working with Text Data :

Lets create of series of Name 
```
In [2]: import pandas as pd

In [3]: name = pd.Series(['Himanshu', 'ZeoLearn', 'Internet', 'Blog'])
```
* Convert all names in Lower string 
```
In [4]: name.str.lower()
Out[4]: 
0    himanshu
1    zeolearn
2    internet
3        blog
dtype: object
```
* Convert all names in upper String
```
In [5]: name.str.upper()
Out[5]: 
0    HIMANSHU
1    ZEOLEARN
2    INTERNET
3        BLOG
dtype: object
```
* Find the length of strings
```
In [6]: name.str.len()
Out[6]: 
0    8
1    8
2    8
3    4
dtype: int64
```
* Split the columns 
```
In [7]: name = pd.Series(['Himanshu Awasthi', 'ZeoLearn Technology', 'Internet o
   ...: f Things', 'Blog bapu'])
In [8]: name.str.split(" ", expand=True)
Out[8]: 
          0           1       2
0  Himanshu     Awasthi    None
1  ZeoLearn  Technology    None
2  Internet          of  Things
3      Blog        bapu    None
```
* Concatanation of String 
The content of a Series (or Index) can be concatenated:
```
In [9]: name.str.cat(sep=';')
Out[9]: 'Himanshu Awasthi;ZeoLearn Technology;Internet of Things;Blog bapu'
```
* add index element of one series with index element of another series using join 
```
In [10]: standard = pd.Series(['1a' , '2a', '3a', '4a'])

In [11]: name.str.cat(standard,join='outer')
Out[11]: 
0       Himanshu Awasthi1a
1    ZeoLearn Technology2a
2     Internet of Things3a
3              Blog bapu4a
dtype: object
```
We can use seprator b/w strings, 
```
In [12]: name.str.cat(standard,join='outer', sep=' ;')
Out[12]: 
0       Himanshu Awasthi ;1a
1    ZeoLearn Technology ;2a
2     Internet of Things ;3a
3              Blog bapu ;4a
dtype: object
```

#### Groupby :
**Groupby** is a very powerful pandas method. It helps to perform following operations :
  * Splitting
  * Applying 
  * Combining 
  
Lets create a politics Data Frame & perform operations : 
```
In [13]: politics = {'party':['Congress', 'BJP' , 'SP', 'BSP' , 'Other'], 
    ...: 'number_of_sheat' : [10, 80, 30, 5, 2],
    ...: 'Year' :[2007, 2011, 2015, 2020,2025],
    ...: 'winner_sheats':[80, 70, 92, 86, 90]}

In [14]: df = pd.DataFrame(politics)

In [15]: print (df)
   Year  number_of_sheat     party  winner_sheats
0  2007               10  Congress             80
1  2011               80       BJP             70
2  2015               30        SP             92
3  2020                5       BSP             86
4  2025                2     Other             90
```
Split Data into groups :
There are multiple ways to split an object like −

    * obj.groupby('key')
    * obj.groupby(['key1','key2'])
    * obj.groupby(key,axis=1)

```
In [16]: df.groupby('party').groups
Out[16]: 
{'BJP': Int64Index([1], dtype='int64'),
 'BSP': Int64Index([3], dtype='int64'),
 'Congress': Int64Index([0], dtype='int64'),
 'Other': Int64Index([4], dtype='int64'),
 'SP': Int64Index([2], dtype='int64')}
```
Group by with multiple columns:
```
In [19]: df.groupby(['party', 'Year']).groups
Out[19]: 
{('BJP', 2011): Int64Index([1], dtype='int64'),
 ('BSP', 2020): Int64Index([3], dtype='int64'),
 ('Congress', 2007): Int64Index([0], dtype='int64'),
 ('Other', 2025): Int64Index([4], dtype='int64'),
 ('SP', 2015): Int64Index([2], dtype='int64')}
```
