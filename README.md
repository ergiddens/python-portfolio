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
```python
odds = [1, 3, 5, 7]
print("odds are:", odds)
```

    odds are: [1, 3, 5, 7]



```python
print("first element:", odds[0])
print("last element:", odds[3])
print("negative one element:", odds[-1])
```

    first element: 1
    last element: 7
    negative one element: 7



```python
names = ["Curie", "Darwin", "Turing"]
print("names is originally:", names)
names[1] = "Darwin"
print("final names:", names)
```

    names is originally: ['Curie', 'Darwin', 'Turing']
    final names: ['Curie', 'Darwin', 'Turing']



```python
odds.append(11)
print("after adding a value:", odds)
```

    after adding a value: [1, 3, 5, 7, 11]



```python
removed_element = odds.pop(0)
print("odds after removing first element:", odds)
print("removed element:", removed_element)
```

    odds after removing first element: [3, 5, 7, 11]
    removed element: 1



```python
odds.reverse()
print("odds after reversing:", odds)
```

    odds after reversing: [11, 7, 5, 3]



```python
odds = [3,5,7]
primes = odds
primes.append(2)
print("primes:", primes)
print("odds:", odds)
```

    primes: [3, 5, 7, 2]
    odds: [3, 5, 7, 2]



```python
odds = [3,5,7]
primes = list(odds)
primes.append(2)
print("primes:", primes)
print("odds:", odds)
```

    primes: [3, 5, 7, 2]
    odds: [3, 5, 7]



```python
binomial_name = "Drosophila melanogaster"
group = binomial_name[:10]
species = binomial_name[11:23]
print(species)
```

    melanogaster



```python
chromosomes = ["X","Y","2","3","4"]
autosomes = chromosomes[2:5]
print(autosomes)
last = chromosomes[-1]
print(last)
```

    ['2', '3', '4']
    4



```python
date = "Monday 4 January 2023"
day = date[:6]
print("using zero to begin range:", day)
day = date[:6]
print("omitting beginning index:", day)
```

    using zero to begin range: Monday
    omitting beginning index: Monday



```python
months=["January","February","March","April","May","June","July","August","September","October","November","December"]
end = months[8:12]
print("known last position:", end)
end = months[8:len(months)]
print("using length:", end)
end = months[8:]
print("omitting ending index:", end)
```

    known last position: ['September', 'October', 'November', 'December']
    using length: ['September', 'October', 'November', 'December']
    omitting ending index: ['September', 'October', 'November', 'December']



```python

```

## Using Loops
```python
odds = [1, 3, 5, 7]

print(odds[0])
print(odds[1])
print(odds[2])
print(odds[3])
```

    1
    3
    5
    7



```python
odds = [1, 3, 5]

print(odds[0])
print(odds[1])
print(odds[2])
print(odds[3])
```

    1
    3
    5



    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-2-336d90abe530> in <module>
          4 print(odds[1])
          5 print(odds[2])
    ----> 6 print(odds[3])
    

    IndexError: list index out of range



```python
odds = [1, 3, 5, 7, 9, 11, 13, 15, 17, 19]

for num in odds:
    print(num)
```

    1
    3
    5
    7
    9
    11
    13
    15
    17
    19



```python
length = 0
names = ["Curie", "Darwin", "Turing"]

for value in names:
    length = length + 1

print("There are", length, "names in the list.")
```

    There are 3 names in the list.



```python
name = "Rosalind"

for name in ["Curie", "Darwin", "Turing"]:
    print(name)

print("After the loop, name is", name)
```

    Curie
    Darwin
    Turing
    After the loop, name is Turing



```python
names = ["Curie", "Darwin", "Turing"]

print(len(names))
```

    3



```python

```

## Using Multiple Files
```python
import glob

print(glob.glob("inflammation*.csv"))
```

    ['inflammation-10.csv', 'inflammation-09.csv', 'inflammation-11.csv', 'inflammation-06.csv', 'inflammation-05.csv', 'inflammation-08.csv', 'inflammation-01.csv', 'inflammation-07.csv', 'inflammation-04.csv', 'inflammation-03.csv', 'inflammation-02.csv', 'inflammation-12.csv']



```python
import glob
import numpy
import matplotlib.pyplot

filenames = sorted(glob.glob("inflammation*.csv"))
filenames = filenames[0:3]

for filename in filenames:
    print(filename)
    data = numpy.loadtxt(fname=filename, delimiter=",")

    fig = matplotlib.pyplot.figure(figsize=(10.0, 3.0))

    axes1 = fig.add_subplot(1, 3, 1)
    axes2 = fig.add_subplot(1, 3, 2)
    axes3 = fig.add_subplot(1, 3, 3)

    axes1.set_ylabel("average")
    axes1.plot(numpy.mean(data, axis=0))

    axes2.set_ylabel("max")
    axes2.plot(numpy.amax(data, axis=0))

    axes3.set_ylabel("min")
    axes3.plot(numpy.amin(data, axis=0))

    fig.tight_layout()
    matplotlib.pyplot.show()
```

    inflammation-01.csv



![png](output_1_1.png)


    inflammation-02.csv



![png](output_1_3.png)


    inflammation-03.csv



![png](output_1_5.png)



```python
%matplotlib inline
```


```python

```

## Making Choices
```python
num = 37

if num > 100:
    print("greater")
else:
    print("not greater")

print("done")
```

    not greater
    done



```python
num = 53

print("before conditional")

if num > 100:
    print(num, "is greater than 100")

print("after conditional")
```

    before conditional
    after conditional



```python
num = -3

if num > 0:
    print(num, "is positive")
elif num == 0:
    print(num, "is zero")
else:
    print(num, "is negative")
```

    -3 is negative



```python
num = 0

if num > 0:
    print(num, "is positive")
elif num == 0:
    print(num, "is zero")
else:
    print(num, "is negative")
```

    0 is zero



```python
num = 14

if num > 0:
    print(num, "is positive")
elif num == 0:
    print(num, "is zero")
else:
    print(num, "is negative")
```

    14 is positive



```python
if (1 > 0) and (-1 >= 0):
    print("both parts are true")
else:
    print("at least one part is false")
```

    at least one part is false



```python
if (1 > 0) or (-1 >= 0):
    print("at least one part is true")
else:
    print("both of these are false")
```

    at least one part is true



```python
if (-1 > 0) or (-1 >= 0):
    print("at least one part is true")
else:
    print("both of these are false")
```

    both of these are false



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
max_inflammation_0 = numpy.max(data, axis=0)[0]
max_inflammation_20 = numpy.max(data, axis=0)[20]

if max_inflammation_0 == 0 and max_inflammation_20 == 20:
    print("suspicious looking maxima")
elif numpy.sum(numpy.min(data, axis=0)) == 0:
    print("minima add up to zero")
else:
    print("seems okay")
```

    suspicious looking maxima



```python
data = numpy.loadtxt(
    fname="inflammation-03.csv",
    delimiter=","
)
```


```python
max_inflammation_0 = numpy.max(data, axis=0)[0]
max_inflammation_20 = numpy.max(data, axis=0)[20]

if max_inflammation_0 == 0 and max_inflammation_20 == 20:
    print("suspicious looking maxima")
elif numpy.sum(numpy.min(data, axis=0)) == 0:
    print("minima add up to zero; healthy participant?")
else:
    print("seems okay")
```

    minima add up to zero; healthy participant?



```python

```

## Functions 1, 2, 3, and 4
```python
fahrenheit_val = 99
celsius = (fahrenheit_val - 32) * 5 / 9
print(celsius)

fahrenheit_val2 = 43
celsius2 = (fahrenheit_val2 - 32) * 5 / 9
print(celsius2)
```

    37.22222222222222
    6.111111111111111



```python
def fahr_to_celsius_explicit(temp):
    converted = (temp - 32) * 5 / 9
    return converted

def fahr_to_celsius(temp):
    return (temp - 32) * 5 / 9

fahr_to_celsius(32)
fahr_to_celsius_explicit(32)
```




    0.0




```python
print("Freezing point of water:", fahr_to_celsius(32))
print("Boiling point of water:", fahr_to_celsius(212))
```

    Freezing point of water: 0.0
    Boiling point of water: 100.0



```python
def celsius_to_kelvin(temp_c):
    return temp_c + 273.15

print("Freezing point of water in Kelvin:", celsius_to_kelvin(0))
```

    Freezing point of water in Kelvin: 273.15



```python
def fahr_to_kelvin(temp_f):
    temp_c = fahr_to_celsius(temp_f)
    temp_k = celsius_to_kelvin(temp_c)
    return temp_k

print("Boiling point of water in Kelvin:", fahr_to_kelvin(212))
```

    Boiling point of water in Kelvin: 373.15



```python
try:
    print(temp_k)
except NameError as e:
    print(e)
```

    name 'temp_k' is not defined



```python
kelvin = fahr_to_kelvin(212.0)
print("Temperature in Kelvin was", kelvin)
```

    Temperature in Kelvin was 373.15



```python
def print_temperatures():
    print("Temperature in Fahrenheit was", fahr)
    print("Temperature in Kelvin was", kelvin)

fahr = 212.0
kelvin = fahr_to_kelvin(fahr)
print_temperatures()
```

    Temperature in Fahrenheit was 212.0
    Temperature in Kelvin was 373.15



```python

```
```python
import numpy
import matplotlib.pyplot
import matplotlib.pyplot as plt
import glob
```


```python
def visualize(filename):
    data = numpy.loadtxt(fname=filename, delimiter=",")

    fig = plt.figure(figsize=(10.0,3.0))

    axes1 = fig.add_subplot(1,3,1)
    axes2 = fig.add_subplot(1,3,2)
    axes3 = fig.add_subplot(1,3,3)

    axes1.set_ylabel("average")
    axes1.plot(numpy.mean(data, axis=0))

    axes2.set_ylabel("max")
    axes2.plot(numpy.amax(data, axis=0))

    axes3.set_ylabel("min")
    axes3.plot(numpy.amin(data, axis=0))

    fig.tight_layout()
    plt.show()
```


```python
def detect_problems(filename):
    data = numpy.loadtxt(fname=filename, delimiter=",")

    if numpy.amax(data, axis=0)[0] == 0 and numpy.amax(data, axis=0)[20] == 20:
        print("Suspicious looking maxima!")
    elif numpy.sum(numpy.amin(data, axis=0)) == 0:
        print("Minima add up to zero!")
    else:
        print("Seems OK!")
```


```python
filenames = sorted(glob.glob("inflammation*.csv"))

for filename in filenames[:3]:
    print(filename)
    visualize(filename)
    detect_problems(filename)
```

    inflammation-01.csv



![png](output_3_1.png)


    Suspicious looking maxima!
    inflammation-02.csv



![png](output_3_3.png)


    Suspicious looking maxima!
    inflammation-03.csv



![png](output_3_5.png)


    Minima add up to zero!



```python
for filename in filenames:
    print(filename)
    visualize(filename)
    detect_problems(filename)
```

    inflammation-01.csv



![png](output_4_1.png)


    Suspicious looking maxima!
    inflammation-02.csv



![png](output_4_3.png)


    Suspicious looking maxima!
    inflammation-03.csv



![png](output_4_5.png)


    Minima add up to zero!
    inflammation-04.csv



![png](output_4_7.png)


    Suspicious looking maxima!
    inflammation-05.csv



![png](output_4_9.png)


    Suspicious looking maxima!
    inflammation-06.csv



![png](output_4_11.png)


    Suspicious looking maxima!
    inflammation-07.csv



![png](output_4_13.png)


    Suspicious looking maxima!
    inflammation-08.csv



![png](output_4_15.png)


    Minima add up to zero!
    inflammation-09.csv



![png](output_4_17.png)


    Suspicious looking maxima!
    inflammation-10.csv



![png](output_4_19.png)


    Suspicious looking maxima!
    inflammation-11.csv



![png](output_4_21.png)


    Minima add up to zero!
    inflammation-12.csv



![png](output_4_23.png)


    Suspicious looking maxima!



```python

```
```python
import numpy
```


```python
def offset_mean(data, target_mean_value):
    return data - numpy.mean(data) + target_mean_value
```


```python
z = numpy.zeros((2,2))
print(offset_mean(z, 3))
```

    [[3. 3.]
     [3. 3.]]



```python
data = numpy.loadtxt(fname="inflammation-01.csv", delimiter=",")
print(offset_mean(data, 0))
```

    [[-6.14875 -6.14875 -5.14875 ... -3.14875 -6.14875 -6.14875]
     [-6.14875 -5.14875 -4.14875 ... -5.14875 -6.14875 -5.14875]
     [-6.14875 -5.14875 -5.14875 ... -4.14875 -5.14875 -5.14875]
     ...
     [-6.14875 -5.14875 -5.14875 ... -5.14875 -5.14875 -5.14875]
     [-6.14875 -6.14875 -6.14875 ... -6.14875 -4.14875 -6.14875]
     [-6.14875 -6.14875 -5.14875 ... -5.14875 -5.14875 -6.14875]]



```python
print("Original min, mean, max:")
print(numpy.amin(data), numpy.mean(data), numpy.amax(data))

offset_data = offset_mean(data, 0)

print("Offset min, mean, max:")
print(numpy.amin(offset_data), numpy.mean(offset_data), numpy.amax(offset_data))
```

    Original min, mean, max:
    0.0 6.14875 20.0
    Offset min, mean, max:
    -6.14875 2.842170943040401e-16 13.85125



```python
print("Standard deviations before and after:")
print(numpy.std(data), numpy.std(offset_data))

print("Difference in standard deviation:")
print(numpy.std(data) - numpy.std(offset_data))
```

    Standard deviations before and after:
    4.613833197118566 4.613833197118566
    Difference in standard deviation:
    0.0



```python
def offset_mean(data, target_mean_value):
    """
    Return a new array containing the original data
    with its mean offset to match the desired value.

    Example
    -------
    >>> offset_mean([1,2,3], 0)
    array([-1., 0., 1.])
    """
    return data - numpy.mean(data) + target_mean_value
```


```python
help(offset_mean)
```

    Help on function offset_mean in module __main__:
    
    offset_mean(data, target_mean_value)
        Return a new array containing the original data
        with its mean offset to match the desired value.
        
        Example
        -------
        >>> offset_mean([1,2,3], 0)
        array([-1., 0., 1.])
    



```python

```
```python
import numpy

data = numpy.loadtxt(
    "inflammation-01.csv",
    delimiter=","
)

print(data.shape)
```

    (60, 40)



```python
# Demonstrating default arguments in numpy.loadtxt
data = numpy.loadtxt(
    "inflammation-01.csv",
    delimiter=","
)

print(data.shape)
```

    (60, 40)



```python
def offset_mean(data, target_mean_value=0.0):
    """
    Return a new array containing the original data
    with its mean offset to match the desired value.
    By default the target mean is 0.0.

    Example
    -------
    >>> offset_mean([1,2,3])
    array([-1., 0., 1.])
    """
    return data - numpy.mean(data) + target_mean_value
```


```python
test_data = numpy.zeros((2,2))

print(offset_mean(test_data, 3))
print(offset_mean(test_data))
```

    [[3. 3.]
     [3. 3.]]
    [[0. 0.]
     [0. 0.]]



```python
def display(a=1, b=2, c=3):
    print("a:", a)
    print("b:", b)
    print("c:", c)

print("No parameters")
display()

print("\nOne parameter")
display(55)

print("\nTwo parameters")
display(55, 66)

print("\nOnly setting c")
display(c=77)
```

    No parameters
    a: 1
    b: 2
    c: 3
    
    One parameter
    a: 55
    b: 2
    c: 3
    
    Two parameters
    a: 55
    b: 66
    c: 3
    
    Only setting c
    a: 1
    b: 2
    c: 77



```python
help(numpy.loadtxt)
```

    Help on function loadtxt in module numpy:
    
    loadtxt(fname, dtype=<class 'float'>, comments='#', delimiter=None, converters=None, skiprows=0, usecols=None, unpack=False, ndmin=0, encoding='bytes', max_rows=None)
        Load data from a text file.
        
        Each row in the text file must have the same number of values.
        
        Parameters
        ----------
        fname : file, str, or pathlib.Path
            File, filename, or generator to read.  If the filename extension is
            ``.gz`` or ``.bz2``, the file is first decompressed. Note that
            generators should return byte strings for Python 3k.
        dtype : data-type, optional
            Data-type of the resulting array; default: float.  If this is a
            structured data-type, the resulting array will be 1-dimensional, and
            each row will be interpreted as an element of the array.  In this
            case, the number of columns used must match the number of fields in
            the data-type.
        comments : str or sequence of str, optional
            The characters or list of characters used to indicate the start of a
            comment. None implies no comments. For backwards compatibility, byte
            strings will be decoded as 'latin1'. The default is '#'.
        delimiter : str, optional
            The string used to separate values. For backwards compatibility, byte
            strings will be decoded as 'latin1'. The default is whitespace.
        converters : dict, optional
            A dictionary mapping column number to a function that will parse the
            column string into the desired value.  E.g., if column 0 is a date
            string: ``converters = {0: datestr2num}``.  Converters can also be
            used to provide a default value for missing data (but see also
            `genfromtxt`): ``converters = {3: lambda s: float(s.strip() or 0)}``.
            Default: None.
        skiprows : int, optional
            Skip the first `skiprows` lines, including comments; default: 0.
        usecols : int or sequence, optional
            Which columns to read, with 0 being the first. For example,
            ``usecols = (1,4,5)`` will extract the 2nd, 5th and 6th columns.
            The default, None, results in all columns being read.
        
            .. versionchanged:: 1.11.0
                When a single column has to be read it is possible to use
                an integer instead of a tuple. E.g ``usecols = 3`` reads the
                fourth column the same way as ``usecols = (3,)`` would.
        unpack : bool, optional
            If True, the returned array is transposed, so that arguments may be
            unpacked using ``x, y, z = loadtxt(...)``.  When used with a structured
            data-type, arrays are returned for each field.  Default is False.
        ndmin : int, optional
            The returned array will have at least `ndmin` dimensions.
            Otherwise mono-dimensional axes will be squeezed.
            Legal values: 0 (default), 1 or 2.
        
            .. versionadded:: 1.6.0
        encoding : str, optional
            Encoding used to decode the inputfile. Does not apply to input streams.
            The special value 'bytes' enables backward compatibility workarounds
            that ensures you receive byte arrays as results if possible and passes
            'latin1' encoded strings to converters. Override this value to receive
            unicode arrays and pass strings as input to converters.  If set to None
            the system default is used. The default value is 'bytes'.
        
            .. versionadded:: 1.14.0
        max_rows : int, optional
            Read `max_rows` lines of content after `skiprows` lines. The default
            is to read all the lines.
        
            .. versionadded:: 1.16.0
        
        Returns
        -------
        out : ndarray
            Data read from the text file.
        
        See Also
        --------
        load, fromstring, fromregex
        genfromtxt : Load data with missing values handled as specified.
        scipy.io.loadmat : reads MATLAB data files
        
        Notes
        -----
        This function aims to be a fast reader for simply formatted files.  The
        `genfromtxt` function provides more sophisticated handling of, e.g.,
        lines with missing values.
        
        .. versionadded:: 1.10.0
        
        The strings produced by the Python float.hex method can be used as
        input for floats.
        
        Examples
        --------
        >>> from io import StringIO   # StringIO behaves like a file object
        >>> c = StringIO(u"0 1\n2 3")
        >>> np.loadtxt(c)
        array([[0., 1.],
               [2., 3.]])
        
        >>> d = StringIO(u"M 21 72\nF 35 58")
        >>> np.loadtxt(d, dtype={'names': ('gender', 'age', 'weight'),
        ...                      'formats': ('S1', 'i4', 'f4')})
        array([(b'M', 21, 72.), (b'F', 35, 58.)],
              dtype=[('gender', 'S1'), ('age', '<i4'), ('weight', '<f4')])
        
        >>> c = StringIO(u"1,0,2\n3,0,4")
        >>> x, y = np.loadtxt(c, delimiter=',', usecols=(0, 2), unpack=True)
        >>> x
        array([1., 3.])
        >>> y
        array([2., 4.])
    



```python
help(offset_mean)
```

    Help on function offset_mean in module __main__:
    
    offset_mean(data, target_mean_value=0.0)
        Return a new array containing the original data
        with its mean offset to match the desired value.
        By default the target mean is 0.0.
        
        Example
        -------
        >>> offset_mean([1,2,3])
        array([-1., 0., 1.])
    



```python

```

## Defensive Programming
```python
numbers = [1.5, 0.3, 0.7, -0.001, 4.4]

total = 0.0

for num in numbers:
    assert num > 0.0, "Data should only contain positive values"
    total += num

print("Total is", total)
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-1-8a8d77df131a> in <module>
          4 
          5 for num in numbers:
    ----> 6     assert num > 0.0, "Data should only contain positive values"
          7     total += num
          8 


    AssertionError: Data should only contain positive values



```python
def normalize_rectangle(rect):
    """
    Normalize a rectangle so that it is at the origin
    and 1.0 units long on its longest axis.

    Input format: (x0, y0, x1, y1)
    """

    assert len(rect) == 4, "Rectangles must contain four coordinates"

    x0, y0, x1, y1 = rect

    assert x0 < x1, "Invalid x coordinates"
    assert y0 < y1, "Invalid y coordinates"

    dx = x1 - x0
    dy = y1 - y0

    if dx > dy:
        scale = dx
        upper_x = 1.0
        upper_y = dy / dx
    else:
        scale = dy
        upper_x = dx / dy
        upper_y = 1.0

    assert 0.0 < upper_x <= 1.0, "Calculated upper x coordinate invalid"
    assert 0.0 < upper_y <= 1.0, "Calculated upper y coordinate invalid"

    return (0.0, 0.0, upper_x, upper_y)
```


```python
# Intentionally trigger an assertion
print(normalize_rectangle((0.0, 1.0, 2.0)))
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-3-89a18614a90c> in <module>
          1 # Intentionally trigger an assertion
    ----> 2 print(normalize_rectangle((0.0, 1.0, 2.0)))
    

    <ipython-input-2-7e7b794d9521> in normalize_rectangle(rect)
          7     """
          8 
    ----> 9     assert len(rect) == 4, "Rectangles must contain four coordinates"
         10 
         11     x0, y0, x1, y1 = rect


    AssertionError: Rectangles must contain four coordinates



```python
# Invalid x coordinates
print(normalize_rectangle((4.0, 2.0, 1.0, 5.0)))
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-4-ebabec9a69a4> in <module>
          1 # Invalid x coordinates
    ----> 2 print(normalize_rectangle((4.0, 2.0, 1.0, 5.0)))
    

    <ipython-input-2-7e7b794d9521> in normalize_rectangle(rect)
         11     x0, y0, x1, y1 = rect
         12 
    ---> 13     assert x0 < x1, "Invalid x coordinates"
         14     assert y0 < y1, "Invalid y coordinates"
         15 


    AssertionError: Invalid x coordinates



```python
# Valid rectangle
print(normalize_rectangle((0.0, 0.0, 1.0, 5.0)))
```

    (0.0, 0.0, 0.2, 1.0)



```python
# Wider than tall
print(normalize_rectangle((0.0, 0.0, 5.0, 1.0)))
```

    (0.0, 0.0, 1.0, 0.2)



```python

```
```python
# Defensive Programming Part 2
# This lesson is discussion-based. These notes summarize the key debugging practices.
```


```python
debugging_tips = [
    "Know what your program is supposed to do.",
    "Create a test that fails every time.",
    "Make failures happen quickly.",
    "Change one thing at a time.",
    "Keep track of what you've tried.",
    "Ask for help when needed."
]

for tip in debugging_tips:
    print("-", tip)
```

    - Know what your program is supposed to do.
    - Create a test that fails every time.
    - Make failures happen quickly.
    - Change one thing at a time.
    - Keep track of what you've tried.
    - Ask for help when needed.



```python
def check_positive(values):
    for v in values:
        assert v >= 0, "Negative values are not allowed."
    return True

print(check_positive([1, 2, 3]))
```

    True



```python
# Example: changing one thing at a time
x = 10
y = 5

print("Before:", x, y)
x = x + 1
print("After changing one variable:", x, y)
```

    Before: 10 5
    After changing one variable: 11 5



```python
print(
"""Key Takeaways

1. Understand what the code should do.
2. Reproduce bugs consistently.
3. Make bugs fail quickly.
4. Change one thing at a time.
5. Keep notes.
6. Don't be afraid to ask for help.
""")
```

    Key Takeaways
    
    1. Understand what the code should do.
    2. Reproduce bugs consistently.
    3. Make bugs fail quickly.
    4. Change one thing at a time.
    5. Keep notes.
    6. Don't be afraid to ask for help.
    



```python

```

## Transcribing DNA into RNA

## Translating RNA into Protein
