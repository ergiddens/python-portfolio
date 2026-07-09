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
```python
import numpy
```


```python
data = numpy.loadtxt(
    fname="inflammation-01.csv",
    delimiter=","
)
```


```python
print(data)
```

    [[0. 0. 1. ... 3. 0. 0.]
     [0. 1. 2. ... 1. 0. 1.]
     [0. 1. 1. ... 2. 1. 1.]
     ...
     [0. 1. 1. ... 1. 1. 1.]
     [0. 0. 0. ... 0. 2. 0.]
     [0. 0. 1. ... 1. 1. 0.]]



```python
print(type(data))
```

    <class 'numpy.ndarray'>



```python
print(data.shape)
```

    (60, 40)



```python
print("First value in data:", data[0, 0])
```

    First value in data: 0.0



```python
print("Middle value in data:", data[29, 19])
```

    Middle value in data: 16.0



```python
print(data[0:4, 0:10])
```

    [[0. 0. 1. 3. 1. 2. 4. 7. 8. 3.]
     [0. 1. 2. 1. 2. 1. 3. 2. 2. 6.]
     [0. 1. 1. 3. 3. 2. 6. 2. 5. 9.]
     [0. 0. 2. 0. 4. 2. 2. 1. 6. 7.]]



```python
print(data[5:10, 0:10])
```

    [[0. 0. 1. 2. 2. 4. 2. 1. 6. 4.]
     [0. 0. 2. 2. 4. 2. 2. 5. 5. 8.]
     [0. 0. 1. 2. 3. 1. 2. 3. 5. 3.]
     [0. 0. 0. 3. 1. 5. 6. 5. 5. 8.]
     [0. 1. 1. 2. 1. 3. 5. 3. 5. 8.]]



```python
small = data[:3, 36:]
print("small is:")
print(small)
```

    small is:
    [[2. 3. 0. 0.]
     [1. 1. 0. 1.]
     [2. 2. 1. 1.]]



```python

```
```python
import numpy
```


```python
data = numpy.loadtxt(
    fname="inflammation-01.csv",
    delimiter=","
)
```


```python
print(data)
```

    [[0. 0. 1. ... 3. 0. 0.]
     [0. 1. 2. ... 1. 0. 1.]
     [0. 1. 1. ... 2. 1. 1.]
     ...
     [0. 1. 1. ... 1. 1. 1.]
     [0. 0. 0. ... 0. 2. 0.]
     [0. 0. 1. ... 1. 1. 0.]]



```python
print(type(data))
```

    <class 'numpy.ndarray'>



```python
print(data.shape)
```

    (60, 40)



```python
print("First value in data:", data[0,0])
```

    First value in data: 0.0



```python
print("Middle value in data:", data[29,19])
```

    Middle value in data: 16.0



```python
print(data[0:4,0:10])
```

    [[0. 0. 1. 3. 1. 2. 4. 7. 8. 3.]
     [0. 1. 2. 1. 2. 1. 3. 2. 2. 6.]
     [0. 1. 1. 3. 3. 2. 6. 2. 5. 9.]
     [0. 0. 2. 0. 4. 2. 2. 1. 6. 7.]]



```python
print(data[5:10,0:10])
```

    [[0. 0. 1. 2. 2. 4. 2. 1. 6. 4.]
     [0. 0. 2. 2. 4. 2. 2. 5. 5. 8.]
     [0. 0. 1. 2. 3. 1. 2. 3. 5. 3.]
     [0. 0. 0. 3. 1. 5. 6. 5. 5. 8.]
     [0. 1. 1. 2. 1. 3. 5. 3. 5. 8.]]



```python
small = data[:3,36:]
print("small is:")
print(small)
```

    small is:
    [[2. 3. 0. 0.]
     [1. 1. 0. 1.]
     [2. 2. 1. 1.]]



```python
print(numpy.mean(data))
```

    6.14875



```python
maxval, minval, stdval = numpy.max(data), numpy.min(data), numpy.std(data)

print(maxval)
print(minval)
print(stdval)
```

    20.0
    0.0
    4.613833197118566



```python
print("maximum inflammation:", maxval)
print("minimum inflammation:", minval)
print("standard deviation:", stdval)
```

    maximum inflammation: 20.0
    minimum inflammation: 0.0
    standard deviation: 4.613833197118566



```python
patient_0 = data[0,:]
print("maximum inflammation for patient 0:", numpy.max(patient_0))
```

    maximum inflammation for patient 0: 18.0



```python
print("maximum inflammation for patient 2:", numpy.max(data[2,:]))
```

    maximum inflammation for patient 2: 19.0



```python
print(numpy.mean(data, axis=0))
```

    [ 0.          0.45        1.11666667  1.75        2.43333333  3.15
      3.8         3.88333333  5.23333333  5.51666667  5.95        5.9
      8.35        7.73333333  8.36666667  9.5         9.58333333 10.63333333
     11.56666667 12.35       13.25       11.96666667 11.03333333 10.16666667
     10.          8.66666667  9.15        7.25        7.33333333  6.58333333
      6.06666667  5.95        5.11666667  3.6         3.3         3.56666667
      2.48333333  1.5         1.13333333  0.56666667]



```python
print(numpy.mean(data, axis=1))
```

    [5.45  5.425 6.1   5.9   5.55  6.225 5.975 6.65  6.625 6.525 6.775 5.8
     6.225 5.75  5.225 6.3   6.55  5.7   5.85  6.55  5.775 5.825 6.175 6.1
     5.8   6.425 6.05  6.025 6.175 6.55  6.175 6.35  6.725 6.125 7.075 5.725
     5.925 6.15  6.075 5.75  5.975 5.725 6.3   5.9   6.75  5.925 7.225 6.15
     5.95  6.275 5.7   6.1   6.825 5.975 6.725 5.7   6.25  6.4   7.05  5.9  ]



```python

```
```python
import numpy
```


```python
import matplotlib.pyplot
```


```python
data = numpy.loadtxt(
    fname="inflammation-01.csv",
    delimiter=","
)
```


```python
image = matplotlib.pyplot.imshow(data)
matplotlib.pyplot.title("Heat Map of Patient Inflammation Over Time")
matplotlib.pyplot.show()
```


![png](output_3_0.png)



```python
ave_inflammation = numpy.mean(data, axis=0)

ave_plot = matplotlib.pyplot.plot(ave_inflammation)
matplotlib.pyplot.show()
```


![png](output_4_0.png)



```python
max_plot = matplotlib.pyplot.plot(numpy.max(data, axis=0))
matplotlib.pyplot.show()
```


![png](output_5_0.png)



```python
min_plot = matplotlib.pyplot.plot(numpy.min(data, axis=0))
matplotlib.pyplot.show()
```


![png](output_6_0.png)



```python
fig = matplotlib.pyplot.figure(figsize=(10.0, 3.0))

axes1 = fig.add_subplot(1, 3, 1)
axes2 = fig.add_subplot(1, 3, 2)
axes3 = fig.add_subplot(1, 3, 3)

axes1.set_ylabel("average")
axes1.plot(numpy.mean(data, axis=0))

axes2.set_ylabel("max")
axes2.plot(numpy.max(data, axis=0))

axes3.set_ylabel("min")
axes3.plot(numpy.min(data, axis=0))

fig.tight_layout()
matplotlib.pyplot.savefig("inflammation.png")
matplotlib.pyplot.show()
```


![png](output_7_0.png)



```python

```

## Storing Values in Lists

## Using Loops

## Using Multiple Files

## Making Choices

## Functions 1, 2, 3, and 4

## Defensive Programming

## Transcribing DNA into RNA

## Translating RNA into Protein
