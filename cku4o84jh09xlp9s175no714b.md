---
title: "Built-in Functions in Python"
seoTitle: "Built-in Functions in Python"
seoDescription: "Built-in Functions in Python"
datePublished: Tue Sep 28 2021 22:48:26 GMT+0000 (Coordinated Universal Time)
cuid: cku4o84jh09xlp9s175no714b
slug: built-in-functions-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1632869265775/5rrzS73X4.webp
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1632869287097/kmQPDVZp_.webp
tags: python, python-beginner

---

The Python interpreter has a number of functions and types built into it that are always available. They are listed here in alphabetical order.

![built-in.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632869220136/HoEi-mIdR.png)

## Python abs()

The abs() function returns the absolute value of the given number. If the number is a complex number, abs() returns its magnitude.


```python
number = -20

absolute_number = abs(number)
print(absolute_number)

# Output: 20
```

    20
    

## Python all()

The all() function returns True if all elements in the given iterable are true. If not, it returns False.



```python
boolean_list = ['True', 'True', 'True']

# check if all elements are true
result = all(boolean_list)
print(result)

# Output: True
```

    True
    

## Python any()

The any() function returns True if any element of an iterable is True. If not, it returns False.


```python
boolean_list = ['True', 'False', 'True']

# check if any element is true
result = any(boolean_list)
print(result)

# Output: True
```

    True
    

## Python ascii()

The ascii() method returns a string containing a printable representation of an object. It escapes the non-ASCII characters in the string using \x, \u or \U escapes.




```python
otherText = 'Pythön is interesting'
print(ascii(otherText))
```

    'Pyth\xf6n is interesting'
    

## Python bin()
The bin() method converts and returns the binary equivalent string of a given integer. If the parameter isn't an integer, it has to implement __index__() method to return an integer.


```python
number = 5
print('The binary equivalent of 5 is:', bin(number))
```

    The binary equivalent of 5 is: 0b101
    

## Python enumerate()
The enumerate() method adds a counter to an iterable and returns it (the enumerate object).


```python
languages = ['Python', 'Java', 'JavaScript']

enumerate_prime = enumerate(languages)

# convert enumerate object to list
print(list(enumerate_prime))

# Output: [(0, 'Python'), (1, 'Java'), (2, 'JavaScript')]
```

    [(0, 'Python'), (1, 'Java'), (2, 'JavaScript')]
    

## Python filter()
The filter() function extracts elements from an iterable (list, tuple etc.) for which a function returns True.


```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# returns True if number is even
def check_even(number):
    if number % 2 == 0:
          return True  

    return False

# Extract elements from the numbers list for which check_even() returns True
even_numbers_iterator = filter(check_even, numbers)

# converting to list
even_numbers = list(even_numbers_iterator)

print(even_numbers)

# Output: [2, 4, 6, 8, 10]
```

    [2, 4, 6, 8, 10]
    

## Python map()

The map() function applies a given function to each item of an iterable (list, tuple etc.) and returns an iterator.


```python
numbers = [2, 4, 6, 8, 10]

# returns square of a number
def square(number):
    return number * number

# apply square() function to each item of the numbers list
squared_numbers_iterator = map(square, numbers)

# converting to list
squared_numbers = list(squared_numbers_iterator)
print(squared_numbers)

# Output: [4, 16, 36, 64, 100]
```

    [4, 16, 36, 64, 100]
    

## Python pow()
The pow() function returns the power of a number.


```python
# positive x, positive y (x**y)
print(pow(2, 2))    # 4

# negative x, positive y
print(pow(-2, 2))    # 4  

# positive x, negative y
print(pow(2, -2))    # 0.25

# negative x, negative y
print(pow(-2, -2))    # 0.25
```

    4
    4
    0.25
    0.25
    

## Python reversed()
The reversed() function returns the reversed iterator of the given sequence.


```python
# for string
seq_string = 'Python'
print(list(reversed(seq_string)))

# for tuple
seq_tuple = ('P', 'y', 't', 'h', 'o', 'n')
print(list(reversed(seq_tuple)))

# for range
seq_range = range(5, 9)
print(list(reversed(seq_range)))

# for list
seq_list = [1, 2, 4, 3, 5]
print(list(reversed(seq_list)))
```

    ['n', 'o', 'h', 't', 'y', 'P']
    ['n', 'o', 'h', 't', 'y', 'P']
    [8, 7, 6, 5]
    [5, 3, 4, 2, 1]
    

## Python round()
The round() function returns a floating-point number rounded to the specified number of decimals.


```python
number = 13.46

# round the number
rounded_number = round(number)
print(rounded_number)

# Output: 13
```

    13
    

## Python sorted()
The sorted() function sorts the elements of a given iterable in a specific order (ascending or descending) and returns it as a list.


```python
numbers = [4, 2, 12, 8]

sorted_numbers = sorted(numbers)
print(sorted_numbers)

# Output: [2, 4, 8, 12]
```

    [2, 4, 8, 12]
    

## Python zip()
The zip() function takes iterables (can be zero or more), aggregates them in a tuple, and returns it.



```python
languages = ['Java', 'Python', 'JavaScript']
versions = [14, 3, 6]

result = zip(languages, versions)
print(list(result))
```

    [('Java', 14), ('Python', 3), ('JavaScript', 6)]
    

**Note: Find more on [Built-in Function](https://docs.python.org/3/library/functions.html)**
