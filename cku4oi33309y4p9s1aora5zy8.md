---
title: "Python Modules & Packages"
seoTitle: "Python Modules & Packages"
seoDescription: "Python Modules & Packages, Modules Vs Packages, NumPy - Introduction, Pandas - Introduction"
datePublished: Tue Sep 28 2021 22:56:11 GMT+0000 (Coordinated Universal Time)
cuid: cku4oi33309y4p9s1aora5zy8
slug: python-modules-and-packages
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1632869659000/AiHtc0NKJ.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1632869690308/5pagg5eU5.png
tags: python, python-beginner

---


If you want your code to be well organized, it’s a good idea to start by grouping related code.**A module is basically a bunch of related code saved in a file with the extension .py.** You may choose to define functions, classes, or variables in a module. It’s also fine to include runnable code in modules.


```python
# welcome.py
def welcome_message(course):
    print("Thank you for subscribing to our " + course + " course. You will get all the details in an email shortly.")
```


```python
import welcome
welcome.welcome_message ("Python Essentials")
```

    Thank you for subscribing to our Python Essentials course. You will get all the details in an email shortly.
    


```python
from welcome import welcome_message
welcome_message ("Python Essentials")
```

    Thank you for subscribing to our Python Essentials course. You will get all the details in an email shortly.
    

If you have some experience with Python, you’ve likely used modules.  For example, you may have used the:

- **random** module to generate pseudo-random number generators for various distributions.
- **html** module to parse HTML pages.
- **datetime** module to manipulate date and time data.
- **re** module to detect and parse regular expressions in Python.

Modules introduce numerous benefits into your Python code:

- Improved development process. Python modules help you focus on one small portion of a task rather than an entire problem. This simplifies the development process and makes it less prone to errors. Furthermore, modules are usually written in a way that minimizes interdependency. Thus, it’s more viable for a team of several programmers to work on the same application.
- The functionality you define in one module can be used in different parts of an application, minimizing duplicate code.Separate namespaces. With Python modules, you can define separate namespaces to avoid collisions between identifiers in different parts of your application.

### Examples


```python
import sys
sys.path
```




    ['C:\\Users\\rahuldubey\\Documents\\My Learnings\\Training\\Python Advance\\6. Modules & Packages',
     'C:\\Users\\rahuldubey\\AppData\\Local\\Continuum\\anaconda3\\python37.zip',
     'C:\\Users\\rahuldubey\\AppData\\Local\\Continuum\\anaconda3\\DLLs',
     'C:\\Users\\rahuldubey\\AppData\\Local\\Continuum\\anaconda3\\lib',
     'C:\\Users\\rahuldubey\\AppData\\Local\\Continuum\\anaconda3',
     '',
     'C:\\Users\\rahuldubey\\AppData\\Roaming\\Python\\Python37\\site-packages',
     'C:\\Users\\rahuldubey\\AppData\\Local\\Continuum\\anaconda3\\lib\\site-packages',
     'C:\\Users\\rahuldubey\\AppData\\Local\\Continuum\\anaconda3\\lib\\site-packages\\win32',
     'C:\\Users\\rahuldubey\\AppData\\Local\\Continuum\\anaconda3\\lib\\site-packages\\win32\\lib',
     'C:\\Users\\rahuldubey\\AppData\\Local\\Continuum\\anaconda3\\lib\\site-packages\\Pythonwin',
     'C:\\Users\\rahuldubey\\AppData\\Local\\Continuum\\anaconda3\\lib\\site-packages\\IPython\\extensions',
     'C:\\Users\\rahuldubey\\.ipython']




```python
import platform

x = platform.system()
print(x)
```

    Windows
    


```python
import datetime

x = datetime.datetime.now()
print(x)
```

    2021-09-22 21:54:34.483628
    


```python
import math

x = math.sqrt(64)

print(x)
```

    8.0
    

## Python Packages

When developing a large application, you may end up with many different modules that are difficult to manage. In such a case, you’ll benefit from grouping and organizing your modules. That’s when packages come into play.

Python packages are basically a directory of a collection of modules. Packages allow the hierarchical structure of the module namespace. Just like we organize our files on a hard drive into folders and sub-folders, we can organize our modules into packages and subpackages.

To be considered a package (or subpackage), a directory must contain a file named __init__.py. This file usually includes the initialization code for the corresponding package.


![package.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632869431132/taAKCZmZC.png)

 **Requests** : The requests package is an HTTP library for Python. It is built on top of urllib3 (another HTTP client for Python), but has a much simpler and more elegant syntax.


```python
import requests
r = requests.get('https://api.spotify.com/')
r.status_code
```




    200



**NumPy** : NumPy is the essential package for scientific and mathematical computing in Python. It introduces n-dimensional arrays and matrices, which are necessary when performing sophisticated mathematical operations. It contains functions that perform basic operations on arrays, such as sorting, shaping, and other mathematical matrix operations. 

For example, to create two 2×2 complex matrices and print the sum: 


```python
import numpy as np

a = np.array([[1+2j, 2+1j], [3, 4]])
b = np.array([[5, 6+6j], [7, 8+4j]])
print(a+b)
```

    [[ 6.+2.j  8.+7.j]
     [10.+0.j 12.+4.j]]
    

**Pandas** : The pandas package introduces a novel data structure, the DataFrame, optimized for tabular, multidimensional, and heterogeneous data. Once your data has been converted to this format, the package provides intuitive and practical means to clean and manipulate it. 

Manipulations such as groupby, join, merge, concatenate data or filling, replacing and imputing null values can be executed in a single line. The developers of the package have the primary goal of producing the world’s most powerful data analysis and manipulation tool that exists in any language — a daunting task that they may actually achieve. 


```python
import pandas as pd

df_1 = pd.DataFrame({'col1': [1,2], 'col2': [3,4]})

df_2 = pd.DataFrame({'col3': [5,6], 'col4': [7,8]})
df = pd.concat([df_1,df_2], axis = 1)
df
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
      <th>col1</th>
      <th>col2</th>
      <th>col3</th>
      <th>col4</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1</td>
      <td>3</td>
      <td>5</td>
      <td>7</td>
    </tr>
    <tr>
      <td>1</td>
      <td>2</td>
      <td>4</td>
      <td>6</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>



## Modules Vs Packages


![mvsp.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632869448863/8hsscah-3.png)

## NumPy - Introduction

NumPy is a Python package. It stands for 'Numerical Python'. It is a library consisting of multidimensional array objects and a collection of routines for processing of array.

Numeric, the ancestor of NumPy, was developed by Jim Hugunin. Another package Numarray was also developed, having some additional functionalities. In 2005, Travis Oliphant created NumPy package by incorporating the features of Numarray into Numeric package. There are many contributors to this open source project.

**Operations using NumPy**

Using NumPy, a developer can perform the following operations −

- Mathematical and logical operations on arrays.

- Fourier transforms and routines for shape manipulation.

- Operations related to linear algebra. NumPy has in-built functions for linear algebra and random number generation.

### NumPy - Environment
Standard Python distribution doesn't come bundled with NumPy module. A lightweight alternative is to install NumPy using popular Python package installer, pip.
```cmd
pip install numpy
```

### NumPy - Ndarray Object
The most important object defined in NumPy is an N-dimensional array type called ndarray. It describes the collection of items of the same type. Items in the collection can be accessed using a zero-based index.


```python
import numpy as np 
a = np.array([1,2,3]) 
print (a)
```

    [1 2 3]
    


```python
import numpy as np 
a = np.array([[1, 2], [3, 4]]) 
print( a)
```

    [[1 2]
     [3 4]]
    


```python
# dtype parameter 
import numpy as np 
a = np.array([1, 2, 3], dtype = complex) 
print( a)
```

    [1.+0.j 2.+0.j 3.+0.j]
    

### NumPy - Array Attributes

**ndarray.shape**
This array attribute returns a tuple consisting of array dimensions. It can also be used to resize the array.


```python
import numpy as np 
a = np.array([[1,2,3],[4,5,6]]) 
print (a.shape)
```

    (2, 3)
    

**ndarray.ndim**
This array attribute returns the number of array dimensions.


```python
# this is one dimensional array 
import numpy as np 
a = np.arange(24) 
print(a.ndim) 

# now reshape it 
b = a.reshape(2,4,3) 
print (b )
# b is having three dimensions
```

    1
    [[[ 0  1  2]
      [ 3  4  5]
      [ 6  7  8]
      [ 9 10 11]]
    
     [[12 13 14]
      [15 16 17]
      [18 19 20]
      [21 22 23]]]
    

**numpy.itemsize**
This array attribute returns the length of each element of array in bytes.


```python
# dtype of array is int8 (1 byte) 
import numpy as np 
x = np.array([1,2,3,4,5], dtype = np.int8) 
print (x.itemsize)
```

    1
    


```python
# dtype of array is now float32 (4 bytes) 
import numpy as np 
x = np.array([1,2,3,4,5], dtype = np.float32) 
print (x.itemsize)
```

    4
    

**numpy.zeros**
Returns a new array of specified size, filled with zeros.


```python
# array of five zeros. Default dtype is float 
import numpy as np 
x = np.zeros(5) 
print( x)
```

    [0. 0. 0. 0. 0.]
    

**numpy.ones**
Returns a new array of specified size and type, filled with ones.


```python
# array of five ones. Default dtype is float 
import numpy as np 
x = np.ones(5) 
print (x)
```

    [1. 1. 1. 1. 1.]
    

**numpy.asarray**
This function is similar to numpy.array except for the fact that it has fewer parameters. This routine is useful for converting Python sequence into ndarray.


```python
# convert list to ndarray 
import numpy as np 

x = [1,2,3] 
a = np.asarray(x) 
print( a)
```

    [1 2 3]
    

**numpy.linspace**
This function is similar to arange() function. In this function, instead of step size, the number of evenly spaced values between the interval is specified. 


```python
import numpy as np 
x = np.linspace(10,20,5) 
print (x)
```

    [10.  12.5 15.  17.5 20. ]
    

For more on [numpy](https://www.tutorialspoint.com/numpy/numpy_quick_guide.htm)

## Pandas - Introduction

Pandas is an open-source Python Library providing high-performance data manipulation and analysis tool using its powerful data structures. The name Pandas is derived from the word Panel Data – an Econometrics from Multidimensional data.

Standard Python distribution doesn't come bundled with Pandas module. A lightweight alternative is to install NumPy using popular Python package installer, pip.
```cmd
pip install pandas
```

Pandas deals with the following three data structures −

- Series
- DataFrame
- Panel

These data structures are built on top of Numpy array, which means they are fast.


![pandas.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632869464120/e-R84HNHbC.png)

**Series**

Series is a one-dimensional array-like structure with homogeneous data. For example, the following series is a collection of integers 10, 23, 56, …


![series.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632869479685/QQZVVXUHU.png)

Key Points
- Homogeneous data
- Size Immutable
- Values of Data Mutable

**DataFrame**

DataFrame is a two-dimensional array with heterogeneous data. For example,


![dataframe.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632869492748/TZ8HBIfv_.png)

Key Points
- Heterogeneous data
- Size Mutable
- Data Mutable

**Panel**

Panel is a three-dimensional data structure with heterogeneous data. It is hard to represent the panel in graphical representation. But a panel can be illustrated as a container of DataFrame.

Key Points
- Heterogeneous data
- Size Mutable
- Data Mutable


```python
#series example

#import the pandas library and aliasing as pd
import pandas as pd
import numpy as np
data = np.array(['a','b','c','d'])
s = pd.Series(data)
print (s)
```

    0    a
    1    b
    2    c
    3    d
    dtype: object
    


```python
#import the pandas library and aliasing as pd
import pandas as pd
import numpy as np
data = np.array(['a','b','c','d'])
s = pd.Series(data,index=[100,101,102,103])
print( s)
```

    100    a
    101    b
    102    c
    103    d
    dtype: object
    


```python
#import the pandas library and aliasing as pd
import pandas as pd
import numpy as np
data = {'a' : 0., 'b' : 1., 'c' : 2.}
s = pd.Series(data,index=['b','c','d','a'])
print (s)
```

    b    1.0
    c    2.0
    d    NaN
    a    0.0
    dtype: float64
    


```python
#dataframe examples
import pandas as pd
data = [1,2,3,4,5]
df = pd.DataFrame(data)
print (df)
```

       0
    0  1
    1  2
    2  3
    3  4
    4  5
    


```python
import pandas as pd
data = [['Alex',10],['Bob',12],['Clarke',13]]
df = pd.DataFrame(data,columns=['Name','Age'])
print (df)
```

         Name  Age
    0    Alex   10
    1     Bob   12
    2  Clarke   13
    


```python
import pandas as pd
data = [['Alex',10],['Bob',12],['Clarke',13]]
df = pd.DataFrame(data,columns=['Name','Age'],dtype=float)
print (df)
```

         Name   Age
    0    Alex  10.0
    1     Bob  12.0
    2  Clarke  13.0
    


```python
import pandas as pd
data = [{'a': 1, 'b': 2},{'a': 5, 'b': 10, 'c': 20}]
df = pd.DataFrame(data)
print (df)
```

       a   b     c
    0  1   2   NaN
    1  5  10  20.0
    

For more on [pandas](https://www.tutorialspoint.com/python_pandas/python_pandas_quick_guide.htm)
