# Python Portfolio

## Introduction

My name is Emma Rose Giddens. This portfolio includes the Python coding work I completed during my introductory computational biology course. It includes practice with Jupyter Notebooks, Python fundamentals, data analysis, loops, functions, defensive programming, and basic bioinformatics tasks including DNA transcription and RNA translation.

## Using Jupyter Notebooks 1 and 2
```python
%matplotlib inline
```


```python
import pandas as pd
```


```python
import matplotlib.pyplot as plt
```


```python
import seaborn as sns
```


```python
sns.set()
```


```python
sns.set_style("darkgrid")
```


```python
df = pd.read_csv("fortune500.csv")
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Rank</th>
      <th>Company</th>
      <th>Revenue (in millions)</th>
      <th>Profit (in millions)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1955</td>
      <td>1</td>
      <td>General Motors</td>
      <td>9823.5</td>
      <td>806</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1955</td>
      <td>2</td>
      <td>Exxon Mobil</td>
      <td>5661.4</td>
      <td>584.8</td>
    </tr>
    <tr>
      <td>2</td>
      <td>1955</td>
      <td>3</td>
      <td>U.S. Steel</td>
      <td>3250.4</td>
      <td>195.4</td>
    </tr>
    <tr>
      <td>3</td>
      <td>1955</td>
      <td>4</td>
      <td>General Electric</td>
      <td>2959.1</td>
      <td>212.6</td>
    </tr>
    <tr>
      <td>4</td>
      <td>1955</td>
      <td>5</td>
      <td>Esmark</td>
      <td>2510.8</td>
      <td>19.1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Rank</th>
      <th>Company</th>
      <th>Revenue (in millions)</th>
      <th>Profit (in millions)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>25495</td>
      <td>2005</td>
      <td>496</td>
      <td>Wm. Wrigley Jr.</td>
      <td>3648.6</td>
      <td>493</td>
    </tr>
    <tr>
      <td>25496</td>
      <td>2005</td>
      <td>497</td>
      <td>Peabody Energy</td>
      <td>3631.6</td>
      <td>175.4</td>
    </tr>
    <tr>
      <td>25497</td>
      <td>2005</td>
      <td>498</td>
      <td>Wendy's International</td>
      <td>3630.4</td>
      <td>57.8</td>
    </tr>
    <tr>
      <td>25498</td>
      <td>2005</td>
      <td>499</td>
      <td>Kindred Healthcare</td>
      <td>3616.6</td>
      <td>70.6</td>
    </tr>
    <tr>
      <td>25499</td>
      <td>2005</td>
      <td>500</td>
      <td>Cincinnati Financial</td>
      <td>3614.0</td>
      <td>584</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.columns
```




    Index(['Year', 'Rank', 'Company', 'Revenue (in millions)',
           'Profit (in millions)'],
          dtype='object')




```python
df.dtypes
```




    Year                       int64
    Rank                       int64
    Company                   object
    Revenue (in millions)    float64
    Profit (in millions)      object
    dtype: object




```python
df.columns
```




    Index(['Year', 'Rank', 'Company', 'Revenue (in millions)',
           'Profit (in millions)'],
          dtype='object')




```python
df.columns = ["year", "rank", "company", "revenue", "profit"]
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>year</th>
      <th>rank</th>
      <th>company</th>
      <th>revenue</th>
      <th>profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1955</td>
      <td>1</td>
      <td>General Motors</td>
      <td>9823.5</td>
      <td>806</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1955</td>
      <td>2</td>
      <td>Exxon Mobil</td>
      <td>5661.4</td>
      <td>584.8</td>
    </tr>
    <tr>
      <td>2</td>
      <td>1955</td>
      <td>3</td>
      <td>U.S. Steel</td>
      <td>3250.4</td>
      <td>195.4</td>
    </tr>
    <tr>
      <td>3</td>
      <td>1955</td>
      <td>4</td>
      <td>General Electric</td>
      <td>2959.1</td>
      <td>212.6</td>
    </tr>
    <tr>
      <td>4</td>
      <td>1955</td>
      <td>5</td>
      <td>Esmark</td>
      <td>2510.8</td>
      <td>19.1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.year.unique()
```




    array([1955, 1956, 1957, 1958, 1959, 1960, 1961, 1962, 1963, 1964, 1965,
           1966, 1967, 1968, 1969, 1970, 1971, 1972, 1973, 1974, 1975, 1976,
           1977, 1978, 1979, 1980, 1981, 1982, 1983, 1984, 1985, 1986, 1987,
           1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998,
           1999, 2000, 2001, 2002, 2003, 2004, 2005])




```python
len(df)
```




    25500




```python
df["profit"].describe()
```




    count     25500
    unique     6977
    top        N.A.
    freq        369
    Name: profit, dtype: object




```python
df["profit"] = df["profit"].replace("N.A.", np.nan)
df["profit"] = pd.to_numeric(df["profit"])
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-19-aaf466ffabe9> in <module>
    ----> 1 df["profit"] = df["profit"].replace("N.A.", np.nan)
          2 df["profit"] = pd.to_numeric(df["profit"])


    NameError: name 'np' is not defined



```python
df = df[df.profit != "N.A."]
```


```python
df.profit = df.profit.apply(pd.to_numeric)
```

    /home/student/anaconda3/lib/python3.7/site-packages/pandas/core/generic.py:5208: SettingWithCopyWarning: 
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead
    
    See the caveats in the documentation: http://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
      self[name] = value



```python
df["profit"].describe()
```




    count    25131.000000
    mean       207.903677
    std       1173.695947
    min     -98696.000000
    25%          8.900000
    50%         35.500000
    75%        150.500000
    max      25330.000000
    Name: profit, dtype: float64




```python
x = df.year.unique()
```


```python
averages = df.loc[:, ["year", "revenue", "profit"]].groupby("year").mean()
```


```python
x = averages.index.values
```


```python
y1 = averages.profit.values
```


```python
def plot(x, y, ax, title, y_label):
    ax.set_ylabel(y_label)
    ax.set_title(title)
    ax.plot(x, y)
    ax.margins(x=0, y=0)
```


```python
fig, ax = plt.subplots()
plot(x, y1, ax, "Increase in mean Fortune 500 company profits from 1955 to 2005", "Profit (millions)")
```


![png](output_26_0.png)



```python
y2 = averages.revenue.values
```


```python
fig, ax = plt.subplots()
plot(x, y2, ax, "Increase in mean Fortune 500 company revenue from 1955 to 2005", "Revenue (millions)")
```


![png](output_28_0.png)



```python
def plot_with_std(x, y, stds, ax, title, y_label):
    ax.fill_between(x, y - stds, y + stds, alpha = 0.2)
    plot(x, y, ax, title, y_label)

fig, (ax1, ax2) = plt.subplots(ncols = 2)
title = 'Increase in mean and std fortune 500 company %s from 1955 to 2005'
stds1 = df.groupby("year").std().profit.values
stds2 = df.groupby("year").std().revenue.values
plot_with_std(x, y1, stds1, ax1, title % 'profits', 'Profit (millions)')
plot_with_std(x, y2, stds2, ax2, title % 'revenues', 'Revenue (millions)')
fig.set_size_inches(14,4)
fig.tight_layout()
```


![png](output_29_0.png)



```python

```

## Python Fundamentals
```python
3 + 5 * 4
```




    23




```python
weight_kg = 60
print(weight_kg)
```

    60



```python
weight0 = "valid"
```


```python
0weight = "invalid"
```


      File "<ipython-input-20-19fd4b6c255e>", line 1
        0weight = "invalid"
              ^
    SyntaxError: invalid syntax




```python
weight = 60
Weight = 75

print(weight)
print(Weight)
```

    60
    75



```python
weight_kg = 60.3
patient_name = "John Smith"
patient_id = "001"
```


```python
weight_lb = 2.2 * weight_kg
print(weight_lb)
```

    132.66



```python
weight_kg = 100.0
print("weight in kilograms is now:", weight_kg)
```

    weight in kilograms is now: 100.0



```python
print(type(weight_kg))
print(type(patient_name))
print(type(patient_id))
```

    <class 'float'>
    <class 'str'>
    <class 'str'>



```python
patient_description = patient_name + " (" + patient_id + ")"
print(patient_description)
```

    John Smith (001)



```python
print(patient_name, "weighs", weight_kg, "kg")
```

    John Smith weighs 100.0 kg



```python
weight_lb = weight_kg * 2.2
print(weight_lb)
```

    220.00000000000003



```python
x = 5
y = x * 2
z = y + 3

print(x)
print(y)
print(z)
```

    5
    10
    13



```python
weight_kg = 60
weight_kg = weight_kg + 2

print(weight_kg)
```

    62



```python
patient_id = "002"
patient_description = patient_name + " (" + patient_id + ")"

print(patient_description)
```

    John Smith (002)



```python
print(patient_name)
print(patient_id)
print(weight_kg)
print(weight_lb)
```

    John Smith
    002
    62
    220.00000000000003



```python

```

## Analyzing Data 1, 2, and 3

## Storing Values in Lists

## Using Loops

## Using Multiple Files

## Making Choices

## Functions 1, 2, 3, and 4

## Defensive Programming

## Transcribing DNA into RNA

## Translating RNA into Protein
