---
title: "Conditional Statements in Python"
seoTitle: "Conditional Statements in Python"
seoDescription: "Conditional Statements in Python, Conditional Operator  in python, Ternary operators in python"
datePublished: Tue Sep 28 2021 21:40:17 GMT+0000 (Coordinated Universal Time)
cuid: cku4lshmb09prrps158tu0skv
slug: conditional-statements-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1632865048594/QtZbwAoXH.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1632865167253/wZLPAfgpW.png
tags: python3, python-beginner

---

Conditional Statement in Python perform different computations or actions depending on whether a specific Boolean constraint evaluates to true or false. Conditional statements are handled by IF statements in Python.


```python
if True:
    print("if True")
elif False:
    print("elif True")
else:
    print("neither True")
```

    if True
    

## Conditional Operator

- **Comparison Operator** : 

![comparison operator.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632865088924/-Fd4FkLgX.png)



```python
a=5
b=7
if a<b:
    print("a is less than b")
elif a>b:
    print("a is greater than b")
else:
    print("a is equal to b")
```

    a is less than b
    

- **Identity Operator** :

![identity operator.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632865104848/uKwfwhlIP.png)


```python
x=2
y=2.0
z="2"

if x is y:
    print("x and y  are same")
elif x is z:
    print("x and z are same ")
elif y is not z:
    print("y and z are  not same")
else: 
    print("all are different")
```

    all are different
    

- **Membership Operator** : 

![membership operator.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632865117136/OaOoaGAL1.png)

```python
x = [1,2,3,4,5,6,7,8,9]
y = 8
z= 0
if y in x:
    print("Y is in X List")
    
if z not in x:
    print("Z is not in X List")

```

    Y is in X List
    Z is not in X List
    

## Ternary operators

Ternary operators are also known as conditional expressions are operators that evaluate something based on a condition being true or false. It was added to Python in version 2.5. 


```python
# Program to demonstrate conditional operator
a, b = 10, 20

# Copy value of a in min if a < b else copy b
min = a if a < b else b

print(min)

```

    10
    


```python
# Python program to demonstrate ternary operator
a, b = 10, 20

# Use tuple for selecting an item
# (if_test_false,if_test_true)[test]
# if [a<b] is true it return 1, so element with 1 index will print
# else if [a<b] is false it return 0, so element with 0 index will print
print( (b, a) [a < b] )

# Use Dictionary for selecting an item
# if [a < b] is true then value of True key will print
# elif [a<b] is false then value of False key will print
print({True: a, False: b} [a < b])


```

    10
    10
    


```python
# Python program to demonstrate nested ternary operator
a, b = 10, 20

print ("Both a and b are equal" if a == b else "a is greater than b"
		if a > b else "b is greater than a")

```

    b is greater than a
    
