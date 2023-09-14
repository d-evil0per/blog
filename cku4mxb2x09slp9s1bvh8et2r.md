---
title: "Data Structure in Python"
seoTitle: "Data Structure in Python"
seoDescription: "Lists, List indexing and slicing, List Comprehension, Tuples, Dictionaries, Sets, Union of Sets, Intersection of Sets, Difference of Sets,Compare Sets"
datePublished: Tue Sep 28 2021 22:12:01 GMT+0000 (Coordinated Universal Time)
cuid: cku4mxb2x09slp9s1bvh8et2r
slug: data-structure-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1632867003843/BM9AUlmwg.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1632867026126/xePqhzBYQ.png
tags: python, python-beginner

---

## Lists

Lists are the basic ordered and mutable data collection type in Python. They can be defined with comma-separated values between square brackets; for example, here is a list of the first several prime numbers:


```python
L = [2, 3, 5, 7]
```

Lists have a number of useful properties and methods available to them. Here we'll take a quick look at some of the more common and useful ones:


```python
# Length of a list
len(L)

# Append a value to the end
L.append(11)
print(L)

# Addition concatenates lists
L=L + [13, 17, 19]
print(L)

# sort() method sorts in-place
L = [2, 5, 1, 6, 3, 4]
L.sort()
print(L)

L = [1, 'two', 3.14, [0, 3, 5]]
print(L)
```

    [2, 3, 5, 7, 11]
    [2, 3, 5, 7, 11, 13, 17, 19]
    [1, 2, 3, 4, 5, 6]
    [1, 'two', 3.14, [0, 3, 5]]
    

### List indexing and slicing

Python provides access to elements in compound types through indexing for single elements, and slicing for multiple elements. As we'll see, both are indicated by a square-bracket syntax. Suppose we return to our list of the first several primes:


```python

L = [2, 3, 5, 7, 11]

# indexing
print(L[2])
print(L[-2])
```

    5
    7
    

You can visualize this indexing scheme this way:


![list-indexing.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632866854330/mon3xwfwI.png)

Where indexing is a means of fetching a single value from the list, slicing is a means of accessing multiple values in sub-lists. It uses a colon to indicate the start point (inclusive) and end point (non-inclusive) of the sub-array. For example, to get the first three elements of the list, we can write:


```python
#slicing
print(L[0:3])
print(L[:3])
print(L[-3:])
print(L[::2] ) # equivalent to L[0:len(L):2]
print(L[::-1])
```

    [2, 3, 5]
    [2, 3, 5]
    [5, 7, 11]
    [2, 5, 11]
    [11, 7, 5, 3, 2]
    

## adding and removing items 

- **Update**- You can update single or multiple elements of lists by giving the slice on the left-hand side of the assignment operator, and you can add to elements in a list with the append() method.
- **delete** - To remove a list element, you can use either the del statement if you know exactly which element(s) you are deleting or the remove() method if you do not know.


```python
list1 = ['physics', 'chemistry', 1997, 2000]
print( "Value available at index 2 : ")
print( list1[2])

list1[2] = 2001
print ("New value available at index 2 : ")
print (list1[2])

list1.append("Mathematics")
print(list1)
```

    Value available at index 2 : 
    1997
    New value available at index 2 : 
    2001
    ['physics', 'chemistry', 2001, 2000, 'Mathematics']
    


```python
list1 = ['physics', 'chemistry', 1997, 2000]
print (list1)

# delete using index 
del list1[2]
print( "After deleting value at index 2 : ")
print( list1)

#remove using values
list1.remove(2000)
print(list1)

#pop the last item
list1.pop()
print(list1)

#appending to list
list1.append("chemistry")
list1.append("mathematics")
print(list1)

# pop from any index
list1.pop(1)
print(list1)
```

    ['physics', 'chemistry', 1997, 2000]
    After deleting value at index 2 : 
    ['physics', 'chemistry', 2000]
    ['physics', 'chemistry']
    ['physics']
    ['physics', 'chemistry', 'mathematics']
    ['physics', 'mathematics']
    

## Basic List Operations

Lists respond to the + and * operators much like strings; they mean concatenation and repetition here too, except that the result is a new list, not a string.


![list-operation.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632866871475/zY_3CT3J2.png)

## List Comprehension
List comprehension offers a shorter syntax when you want to create a new list based on the values of an existing list.

**Syntax:**
```Python
newList = [ expression(element) for element in oldList if condition ]
```
learn more on [List Comprehension](https://www.geeksforgeeks.org/python-list-comprehension/)


```python
# without list comprehension

fruits = ["apple", "banana", "cherry", "kiwi", "mango"]
newlist = []

for x in fruits:
    if "a" in x:
        newlist.append(x)

print(newlist)

```

    ['apple', 'banana', 'mango']
    


```python
# with list comprehension

fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

newlist = [x for x in fruits if "a" in x]

print(newlist)
```

    ['apple', 'banana', 'mango']
    

## Tuples

A tuple is a sequence of immutable Python objects. Tuples are sequences, just like lists. The differences between tuples and lists are, the tuples cannot be changed unlike lists and tuples use parentheses, whereas lists use square brackets.

```Python
tup1 = ('physics', 'chemistry', 1997, 2000)
tup2 = (1, 2, 3, 4, 5 )
tup3 = "a", "b", "c", "d"
```

### Accessing Values in Tuples
To access values in tuple, use the square brackets for slicing along with the index or indices to obtain value available at that index.


```python
tup1 = ('physics', 'chemistry', 1997, 2000)
tup2 = (1, 2, 3, 4, 5, 6, 7 )
print ("tup1[0]: ", tup1[0])
print ("tup2[1:5]: ", tup2[1:5])
```

    tup1[0]:  physics
    tup2[1:5]:  (2, 3, 4, 5)
    

### Updating Tuples
Tuples are immutable which means you cannot update or change the values of tuple elements. You are able to take portions of existing tuples to create new tuples.


```python
tup1 = (12, 34.56)
tup2 = ('abc', 'xyz')

# Following action is not valid for tuples
# tup1[0] = 100;

# So let's create a new tuple as follows
tup3 = tup1 + tup2
print (tup3)
```

    (12, 34.56, 'abc', 'xyz')
    

### Delete Tuple Elements
Removing individual tuple elements is not possible. There is, of course, nothing wrong with putting together another tuple with the undesired elements discarded.
To explicitly remove an entire tuple, just use the del statement.


```python
tup = ('physics', 'chemistry', 1997, 2000)
print( tup)
del tup
print( tup)
```

    ('physics', 'chemistry', 1997, 2000)
    


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-36-65694b0fbff3> in <module>
          2 print( tup)
          3 del tup
    ----> 4 print( tup)
    

    NameError: name 'tup' is not defined


### Basic Tuples Operations
Tuples respond to the + and * operators much like strings; they mean concatenation and repetition here too, except that the result is a new tuple, not a string.


![tuple operations.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632866891726/oXxmyI8t6.png)

## Dictionaries

In Dictionary each key is separated from its value by a colon (:), the items are separated by commas, and the whole thing is enclosed in curly braces. An empty dictionary without any items is written with just two curly braces, like this − {}.

Keys are unique within a dictionary while values may not be. The values of a dictionary can be of any type, but the keys must be of an immutable data type such as strings, numbers, or tuples.


```python
dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}
print ("dict['Name']: ", dict['Name'])
print ("dict['Age']: ", dict['Age'])
```

    dict['Name']:  Zara
    dict['Age']:  7
    

### Updating Dictionary
You can update a dictionary by adding a new entry or a key-value pair, modifying an existing entry, or deleting an existing entry.



```python
dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}
dict['Age'] = 8; # update existing entry
dict['School'] = "DPS School"; # Add new entry

print( "dict['Age']: ", dict['Age'])
print ("dict['School']: ", dict['School'])
```

    dict['Age']:  8
    dict['School']:  DPS School
    

### Delete Dictionary Elements
You can either remove individual dictionary elements or clear the entire contents of a dictionary. You can also delete entire dictionary in a single operation.


```python
dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}
del dict['Name']; # remove entry with key 'Name'
dict.clear();     # remove all entries in dict


print ("dict['Age']: ", dict['Age'])
print ("dict['School']: ", dict['School'])
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-40-b1280a1224f8> in <module>
          4 # del dict ;        # delete entire dictionary
          5 
    ----> 6 print ("dict['Age']: ", dict['Age'])
          7 print ("dict['School']: ", dict['School'])
    

    KeyError: 'Age'


### Properties of Dictionary Keys

Dictionary values have no restrictions. They can be any arbitrary Python object, either standard objects or user-defined objects. However, same is not true for the keys.

There are two important points to remember about dictionary keys −

- More than one entry per key not allowed. Which means no duplicate key is allowed. When duplicate keys encountered during assignment, the last assignment wins.
- Keys must be immutable. Which means you can use strings, numbers or tuples as dictionary keys but something like ['key'] is not allowed.


```python
dict = {'Name': 'Zara', 'Age': 7, 'Name': 'Manni'}
print ("dict['Name']: ", dict['Name'])
```

    dict['Name']:  Manni
    


```python
dict = {['Name']: 'Zara', 'Age': 7}
print ("dict['Name']: ", dict['Name'])
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-42-d3c59f072d3f> in <module>
    ----> 1 dict = {['Name']: 'Zara', 'Age': 7}
          2 print ("dict['Name']: ", dict['Name'])
    

    TypeError: unhashable type: 'list'


### Built-in Dictionary Methods

- **clear()** : Clears a dictionary.
- **get()**: Returns the value for a key if it exists in the dictionary.
- **items()**: Returns a list of key-value pairs in a dictionary.
- **keys()**: Returns a list of keys in a dictionary.
- **values()**: Returns a list of values in a dictionary.
- **pop()** : Removes a key from a dictionary, if it is present, and returns its value.
- **popitem()**: Removes a key-value pair from a dictionary.
- **update()**: Merges a dictionary with another dictionary or with an iterable of key-value pairs.


```python
d = {'a': 10, 'b': 20, 'c': 30}
print(d.get('b'))
print(d.items()) # items
print(d.keys())
print(d.values())
print(d.pop('b'))
print(d.pop('z', -1))
print(d.popitem())
d.clear()

#update
d1 = {'a': 10, 'b': 20, 'c': 30}
d2 = {'b': 200, 'd': 400}
d1.update(d2)
print(d1)

```

    20
    dict_items([('a', 10), ('b', 20), ('c', 30)])
    dict_keys(['a', 'b', 'c'])
    dict_values([10, 20, 30])
    20
    -1
    ('c', 30)
    {'a': 10, 'b': 200, 'c': 30, 'd': 400}
    

## Sets

Mathematically a set is a collection of items not in any particular order. A Python set is similar to this mathematical definition with below additional conditions.

- The elements in the set cannot be duplicates.

- The elements in the set are immutable(cannot be modified) but the set as a whole is mutable.

- There is no index attached to any element in a python set. So they do not support any indexing or slicing operation.

example:- 
```Python
Days=set(["Mon","Tue","Wed","Thu","Fri","Sat","Sun"])
Months={"Jan","Feb","Mar"}
Dates={21,22,17}
```


```python
x = set(['foo', 'bar', 'baz', 'foo', 'qux'])
x
```




    {'bar', 'baz', 'foo', 'qux'}



### Accessing Values in a Set
We cannot access individual values in a set. We can only access all the elements together as shown above. But we can also get a list of individual elements by looping through the set.


```python
Days=set(["Mon","Tue","Wed","Thu","Fri","Sat","Sun"])
 
for d in Days:
    print(d)
```

    Sun
    Tue
    Mon
    Thu
    Fri
    Sat
    Wed
    

### Adding Items to a Set
We can add elements to a set by using add() method. Again as discussed there is no specific index attached to the newly added element.


```python
Days=set(["Mon","Tue","Wed","Thu","Fri","Sat"])
 
Days.add("Sun")
print(Days)
```

    {'Sun', 'Tue', 'Mon', 'Thu', 'Fri', 'Sat', 'Wed'}
    

### Removing Item from a Set
We can remove elements from a set by using discard() method. Again as discussed there is no specific index attached to the newly added element.


```python
Days=set(["Mon","Tue","Wed","Thu","Fri","Sat"])
 
Days.discard("Sun")
print(Days)
```

    {'Tue', 'Mon', 'Thu', 'Fri', 'Sat', 'Wed'}
    

### Union of Sets
The union operation on two sets produces a new set containing all the distinct elements from both the sets. In the below example the element “Wed” is present in both the sets.


```python
DaysA = set(["Mon","Tue","Wed"])
DaysB = set(["Wed","Thu","Fri","Sat","Sun"])
AllDays = DaysA|DaysB
print(AllDays)
```

    {'Sun', 'Tue', 'Mon', 'Thu', 'Fri', 'Sat', 'Wed'}
    


```python
x1 = {'foo', 'bar', 'baz'}
x2 = {'baz', 'qux', 'quux'}
print(x1|x2)

# x3=(1,2,3)
# print(x1|x3)

print(x1.union(x3))
```

    {'bar', 'baz', 'qux', 'quux', 'foo'}
    {1, 2, 3, 'baz', 'bar', 'foo'}
    

### Intersection of Sets
The intersection operation on two sets produces a new set containing only the common elements from both the sets. In the below example the element “Wed” is present in both the sets.


```python
DaysA = set(["Mon","Tue","Wed"])
DaysB = set(["Wed","Thu","Fri","Sat","Sun"])
AllDays = DaysA & DaysB
print(AllDays)
```

    {'Wed'}
    


```python
x1 = {'foo', 'bar', 'baz'}
x2 = ('baz', 'qux')
print(x1.intersection(x2))
```

    {'baz'}
    

### Difference of Sets
The difference operation on two sets produces a new set containing only the elements from the first set and none from the second set. In the below example the element “Wed” is present in both the sets so it will not be found in the result set.


```python
DaysA = set(["Mon","Tue","Wed"])
DaysB = set(["Wed","Thu","Fri","Sat","Sun"])
AllDays = DaysA - DaysB

print(AllDays)
print(DaysA ^ DaysB)
```

    {'Tue', 'Mon'}
    {'Sun', 'Thu', 'Fri', 'Mon', 'Tue', 'Sat'}
    


```python
x1 = {'foo', 'bar', 'baz'}
x2 = ('baz', 'qux', 'bar')
print(x1.difference(x2))
print(x1.symmetric_difference(x2))
```

    {'foo'}
    {'foo', 'qux'}
    

### Compare Sets
We can check if a given set is a subset or superset of another set. The result is True or False depending on the elements present in the sets.


```python
DaysA = set(["Mon","Tue","Wed"])
DaysB = set(["Mon","Tue","Wed","Thu","Fri","Sat","Sun"])
SubsetRes = DaysA <= DaysB
SupersetRes = DaysB >= DaysA
print(SubsetRes)
print(SupersetRes)
```

    True
    True
    

Learn more on [Sets in python](https://realpython.com/python-sets/)


