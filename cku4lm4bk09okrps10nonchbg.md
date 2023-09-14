---
title: "Types and values in Python"
seoTitle: "Types and values in Python"
seoDescription: "Data Types ( String, Numeric, Boolean, Sequence, Dictionary, Set) in python"
datePublished: Tue Sep 28 2021 21:35:20 GMT+0000 (Coordinated Universal Time)
cuid: cku4lm4bk09okrps10nonchbg
slug: types-and-values-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1632864821278/Ec-5kOu8R.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1632864843455/Rgzjy0Yla.jpeg
tags: python, python-beginner

---


Data types are the classification or categorization of data items. It represents the kind of value that tells what operations can be performed on a particular data. Since everything is an object in Python programming, data types are actually classes and variables are instance (object) of these classes.

![Python-data-structure.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1632864571552/lOxht1uRe.png)

Note – type() function is used to determine the type of data type.

### The String Type

In Python, Strings are arrays of bytes representing Unicode characters. A string is a collection of one or more characters put in a single quote, double-quote or triple quote. In python there is no character data type, a character is a string of length one. It is represented by str class.


```python

# Python Program for 
# Creation of String 
    
# Creating a String  
# with single Quotes 
String1 = 'Welcome to the python training'
print("String with the use of Single Quotes: ") 
print(String1) 
    
# Creating a String 
# with double Quotes 
String1 = "I'm a python lover"
print("\nString with the use of Double Quotes: ") 
print(String1) 
print(type(String1))
    
# Creating a String 
# with triple Quotes 
String1 = '''I'm a python lover and I live in a world of "python"'''
print("\nString with the use of Triple Quotes: ") 
print(String1) 
print(type(String1))
  
# Creating String with triple 
# Quotes allows multiple lines 
String1 = '''python 
            For 
            Life'''
print("\nCreating a multiline String: ") 
print(String1) 
print(type(String1))

String1="python".capitalize()
print(String1)

String1="python".upper()
print(String1)

String1="PYTHON".lower()
print(String1)

String1="python {}.{}".format(3,7)
print(String1)

String1="python {1}.{0}".format(3,7)
print(String1)

String1="string= {:>08}".format(3)
String2="string= {:<08}".format(6)
print(String1)
print(String2)

a=3
b=7
String1=f"python {a}.{b}"
print(String1)
```

    String with the use of Single Quotes: 
    Welcome to the python training
    
    String with the use of Double Quotes: 
    I'm a python lover
    <class 'str'>
    
    String with the use of Triple Quotes: 
    I'm a python lover and I live in a world of "python"
    <class 'str'>
    
    Creating a multiline String: 
    python 
                For 
                Life
    <class 'str'>
    Python
    PYTHON
    python
    python 3.7
    python 7.3
    string= 00000003
    string= 60000000
    python 3.7
    

#### Accessing elements of String

In Python, individual characters of a String can be accessed by using the method of Indexing. Indexing allows negative address references to access characters from the back of the String, e.g. -1 refers to the last character, -2 refers to the second last character and so on.
![main-qimg-90a538637c0511377aec59920d5d4465.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632864713761/t62S6Zcst.png)




```python
# Python Program to Access
# characters of String
	
String1 = "GeeksForGeeks"
print("Initial String: ")
print(String1)
	
# Printing First character
print("\nFirst character of String is: ")
print(String1[0])
	
# Printing Last character
print("\nLast character of String is: ")
print(String1[-1])

# Printing sub String characters
print("\nsub-string  is: ")
print(String1[0:5])


```

    Initial String: 
    GeeksForGeeks
    
    First character of String is: 
    G
    
    Last character of String is: 
    s
    
    sub-string  is: 
    Geeks
    

## Numeric Type

In Python, numeric data type represent the data which has numeric value. Numeric value can be integer, floating number or even complex numbers. These values are defined as int, float and complex class in Python.

- **Integers** – This value is represented by int class. It contains positive or negative whole numbers (without fraction or decimal). In Python there is no limit to how long an integer value can be.
- **Float** – This value is represented by float class. It is a real number with floating point representation. It is specified by a decimal point. Optionally, the character e or E followed by a positive or negative integer may be appended to specify scientific notation.
- **Complex Numbers** – Complex number is represented by complex class. It is specified as (real part) + (imaginary part)j. For example – 2+3j


```python
# Python program to 
# demonstrate numeric value
  
a = 5
print("Type of a: ", type(a))
  
b = 5.0
print("\nType of b: ", type(b))
  
c = 2 + 4j
print("\nType of c: ", type(c))

x= .1+.1+.1 -.3
print(f"\nx is {x}")
```

    Type of a:  <class 'int'>
    
    Type of b:  <class 'float'>
    
    Type of c:  <class 'complex'>
    
    x is 5.551115123125783e-17
    


```python
from decimal import *

a= Decimal(".10")
b= Decimal("0.3")

x= a+a+a-b
print(f"\nx is {x}")
print(f"\nType is {type(x)}")
```

    
    x is 0.00
    
    Type is <class 'decimal.Decimal'>
    

## Boolean

Data type with one of the two built-in values, True or False. Boolean objects that are equal to True are truthy (true), and those equal to False are falsy (false). But non-Boolean objects can be evaluated in Boolean context as well and determined to be true or false. It is denoted by the class bool.

**Note – True and False with capital ‘T’ and ‘F’ are valid booleans otherwise python will throw an error.**


```python
# Python program to
# demonstrate boolean type

print(type(True))
print(type(False))

print(type(true))

```

    <class 'bool'>
    <class 'bool'>
    


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-37-835ffa49952b> in <module>
          5 print(type(False))
          6 
    ----> 7 print(type(true))
    

    NameError: name 'true' is not defined



```python
x= 7>5
print(f"\nx is {x}")
print(f"\nType is {type(x)}")
```

    
    x is True
    
    Type is <class 'bool'>
    


```python
x= None
print(f"\nx is {x}")
print(f"\nType is {type(x)}")
```

    
    x is None
    
    Type is <class 'NoneType'>
    


```python
x= None
if x:
    print(True)
else:
    print(False)
```

    False
    

## Sequence Type

#### List

Lists are just like the arrays, declared in other languages which is a ordered collection of data. It is very flexible as the items in a list do not need to be of the same type.


```python
# Python program to demonstrate
# Creation of List
	
# Creating a List
List = []
print("Intial blank List: ")
print(List)
	
# Creating a List with
# the use of a String
List = ['Hello world']
print("\nList with the use of String: ")
print(List)
	
# Creating a List with
# the use of multiple values
List = ["Bob", "Alice", "Robert"]
print("\nList containing multiple values: ")
print(List[0])
print(List[2])
List.append("Jack")
print(List)
List.remove("Bob")
print(List)
	
# Creating a Multi-Dimensional List
# (By Nesting a list inside a List)
List = [['Bob', 'Alice'], ['Robert']]
print("\nMulti-Dimensional List: ")
print(List[0])
print(List[1])
print(List[0][1])

print(type(List))

```

    Intial blank List: 
    []
    
    List with the use of String: 
    ['Hello world']
    
    List containing multiple values: 
    Bob
    Robert
    ['Bob', 'Alice', 'Robert', 'Jack']
    ['Alice', 'Robert', 'Jack']
    
    Multi-Dimensional List: 
    ['Bob', 'Alice']
    ['Robert']
    Alice
    <class 'list'>
    

#### Tuple

Just like list, tuple is also an ordered collection of Python objects. The only difference between tuple and list is that tuples are immutable i.e. tuples cannot be modified after it is created. It is represented by tuple class.


```python
# Python program to demonstrate
# creation of Set
	
# Creating an empty tuple
Tuple1 = ()
print("Initial empty Tuple: ")
print (Tuple1)
	
# Creating a Tuple with
# the use of Strings
Tuple1 = ('Bob', 'Robert')
print("\nTuple with the use of String: ")
print(Tuple1)
	
# Creating a Tuple with
# the use of list
list1 = [1, 2, 4, 5, 6]
print("\nTuple using List: ")
print(tuple(list1))

# Creating a Tuple with the
# use of built-in function
Tuple1 = tuple('Jack')
print("\nTuple with the use of function: ")
print(Tuple1)

# Creating a Tuple
# with nested tuples
Tuple1 = (0, 1, 2, 3)
Tuple2 = ('python', 'geek')
Tuple3 = (Tuple1, Tuple2)
print("\nTuple with nested tuples: ")
print(Tuple3)
print(type(Tuple3))


x = range(5)
print(x)
print(type(x))
```

    Initial empty Tuple: 
    ()
    
    Tuple with the use of String: 
    ('Bob', 'Robert')
    
    Tuple using List: 
    (1, 2, 4, 5, 6)
    
    Tuple with the use of function: 
    ('J', 'a', 'c', 'k')
    
    Tuple with nested tuples: 
    ((0, 1, 2, 3), ('python', 'geek'))
    <class 'tuple'>
    range(0, 5)
    <class 'range'>
    

## Dictionary

Dictionary in Python is an unordered collection of data values, used to store data values like a map, which unlike other Data Types that hold only single value as an element, Dictionary holds key:value pair. Key-value is provided in the dictionary to make it more optimized. Each key-value pair in a Dictionary is separated by a colon :, whereas each key is separated by a ‘comma’.


```python
# Creating an empty Dictionary
Dict = {}
print("Empty Dictionary: ")
print(Dict)
	
# Creating a Dictionary
# with Integer Keys
Dict = {1: 'Geeks', 2: 'For', 3: 'Geeks'}
print("\nDictionary with the use of Integer Keys: ")
print(Dict)
	
# Creating a Dictionary
# with Mixed keys
Dict = {'Name': 'Geeks', 1: [1, 2, 3, 4]}
print("\nDictionary with the use of Mixed Keys: ")
print(Dict)
	
# Creating a Dictionary
# with dict() method
Dict = dict({1: 'Geeks', 2: 'For', 3:'Geeks'})
print("\nDictionary with the use of dict(): ")
print(Dict)
	
# Creating a Dictionary
# with each item as a Pair
Dict = dict([(1, 'Geeks'), (2, 'For')])
print("\nDictionary with each item as a pair: ")
print(Dict)

```

    Empty Dictionary: 
    {}
    
    Dictionary with the use of Integer Keys: 
    {1: 'Geeks', 2: 'For', 3: 'Geeks'}
    
    Dictionary with the use of Mixed Keys: 
    {'Name': 'Geeks', 1: [1, 2, 3, 4]}
    
    Dictionary with the use of dict(): 
    {1: 'Geeks', 2: 'For', 3: 'Geeks'}
    
    Dictionary with each item as a pair: 
    {1: 'Geeks', 2: 'For'}
    


```python
# Python program to demonstrate
# accessing a element from a Dictionary
	
# Creating a Dictionary
Dict = {1: 'Geeks', 'name': 'For', 3: 'Geeks'}
	
# accessing a element using key
print("Accessing a element using key:")
print(Dict['name'])

# accessing a element using get()
# method
print("Accessing a element using get:")
print(Dict.get(3))

Dict[1]="Python"
print(Dict)
for k,v in Dict.items():
    print(f"key: {k} ,Value: {v}")

```

    Accessing a element using key:
    For
    Accessing a element using get:
    Geeks
    {1: 'Python', 'name': 'For', 3: 'Geeks'}
    key: 1 ,Value: Python
    key: name ,Value: For
    key: 3 ,Value: Geeks
    

## Set

In Python, Set is an unordered collection of data type that is iterable, mutable and has no duplicate elements. The order of elements in a set is undefined though it may consist of various elements.


```python
# Python program to demonstrate
# Creation of Set in Python
	
# Creating a Set
set1 = set()
print("Intial blank Set: ")
print(set1)
	
# Creating a Set with
# the use of a String
set1 = set("GeeksForGeeks")
print("\nSet with the use of String: ")
print(set1)

# Creating a Set with
# the use of a List
set1 = set(["Geeks", "For", "Geeks"])
print("\nSet with the use of List: ")
print(set1)

# Creating a Set with
# a mixed type of values
# (Having numbers and strings)
set1 = set([1, 2, 'Geeks', 4, 'For', 6, 'Geeks'])
print("\nSet with the use of Mixed Values")
print(set1)

```

    Intial blank Set: 
    set()
    
    Set with the use of String: 
    {'G', 's', 'k', 'F', 'e', 'r', 'o'}
    
    Set with the use of List: 
    {'For', 'Geeks'}
    
    Set with the use of Mixed Values
    {1, 2, 'Geeks', 4, 6, 'For'}
    

## id()

- The id() function returns a unique id for the specified object.

- All objects in Python has its own unique id.

- The id is assigned to the object when it is created.

- The id is the object's memory address, and will be different for each time you run the program. (except for some object that has a constant unique id, like integers from -5 to 256)



```python
x=(1,"two",3.0,[4,"four"],5)
y=(1,"two",3.0,[4,"four"],5)

print(id(x))
print(id(y))
```

    2147651435784
    2147688147848
    


```python
x=(1,"two",3.0,[4,"four"],5)
y=(1,"two",3.0,[4,"four"],5)

print(id(x[1]))
print(id(y[1]))

if x[1] is y[1]:
    print("same")
else:
    print("not same")

```

    2147690126832
    2147690126832
    same
    


```python
x=(1,"two",3.0,[4,"four"],5)
y=(1,"two",3.0,[4,"four"],5)

print(id(x))
print(id(y))

if x is y:
    print("same")
else:
    print("not same")
```

    2147688964744
    2147651435784
    not same
    

## isinstance()

The isinstance() function returns True if the specified object is of the specified type, otherwise False.
syntax:
```python
isinstance(object, type)
```


```python
x=(1,"two",3.0,[4,"four"],5)

if type(x) is "tuple":
    print("yes")
else:
    print("No!!")
    
    
if isinstance(x,tuple):
    print("yes")
else:
    print("No!!")
```

    No!!
    yes
    
