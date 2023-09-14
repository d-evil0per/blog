---
title: "Loops in Python"
seoTitle: "Loops in Python"
seoDescription: "While Loop, The Infinite Loop, For Loop, Additional Controls (break statement, continue statement, pass statement)"
datePublished: Tue Sep 28 2021 22:00:19 GMT+0000 (Coordinated Universal Time)
cuid: cku4mi8yd09tarps170vlbsjv
slug: loops-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1632866184472/N7m9kprPC.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1632866315208/CS2e-D9bq.png
tags: python, python3, python-beginner

---


A loop statement allows us to execute a statement or group of statements multiple times. The following diagram illustrates a loop statement −

![loop_architecture.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1632866207618/lyJM5pQ4l.jpeg)

1. **while loop** : Repeats a statement or group of statements while a given condition is TRUE. It tests the condition before executing the loop body.

2. **for loop** : Executes a sequence of statements multiple times and abbreviates the code that manages the loop variable.

3. **nested loops** : You can use one or more loop inside any another while, for or do..while loop.

### While Loop

A while loop statement in Python programming language repeatedly executes a target statement as long as a given condition is true.

**Syntax** : The syntax of a while loop in Python programming language is −

```Python
while expression:
   statement(s)
```

![while loop.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1632866228408/Z7UyqQx5X.jpeg)



```python
count = 0
while (count < 9):
    print ('The count is:', count)
    count = count + 1

print ("Good bye!")
```

    The count is: 0
    The count is: 1
    The count is: 2
    The count is: 3
    The count is: 4
    The count is: 5
    The count is: 6
    The count is: 7
    The count is: 8
    Good bye!
    

#### The Infinite Loop

A loop becomes infinite loop if a condition never becomes FALSE. You must use caution when using while loops because of the possibility that this condition never resolves to a FALSE value. This results in a loop that never ends. Such a loop is called an infinite loop.


```python
var = 1
while var == 1 :  # This constructs an infinite loop
    num = input("Enter a number  :")
    print( "You entered: ", num)

print ("Good bye!")
```

    Enter a number  :2
    You entered:  2
    Enter a number  :3
    You entered:  3
    Enter a number  :4
    You entered:  4
    Enter a number  :1
    You entered:  1
    

#### Using else Statement with While Loop

Python supports to have an else statement associated with a loop statement. If the else statement is used with a while loop, the else statement is executed when the condition becomes false.


```python
count = 0
while count < 5:
    print (count, " is  less than 5")
    count = count + 1
else:
    print (count, " is not less than 5")
```

    0  is  less than 5
    1  is  less than 5
    2  is  less than 5
    3  is  less than 5
    4  is  less than 5
    5  is not less than 5
    

### For Loop

It has the ability to iterate over the items of any sequence, such as a list or a string.

**Syntax**

```Python
for iterating_var in sequence:
   statements(s)
```


![python_for_loop.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1632866246151/PEhdL2fm2.jpeg)


```python
for letter in 'Python':     # First Example
    print ('Current Letter :', letter)

fruits = ['banana', 'apple',  'mango']
for fruit in fruits:        # Second Example
    print ('Current fruit :', fruit)

print ("Good bye!")
```

    Current Letter : P
    Current Letter : y
    Current Letter : t
    Current Letter : h
    Current Letter : o
    Current Letter : n
    Current fruit : banana
    Current fruit : apple
    Current fruit : mango
    Good bye!
    

#### Iterating by Sequence Index

An alternative way of iterating through each item is by index offset into the sequence itself. Following is a simple example −


```python
fruits = ['banana', 'apple',  'mango']
for index in range(len(fruits)):
    print ('Current fruit :', fruits[index])

print ("Good bye!")
```

    Current fruit : banana
    Current fruit : apple
    Current fruit : mango
    Good bye!
    

#### Using else Statement with For Loop

Python supports to have an else statement associated with a loop statement. If the else statement is used with a for loop, the else statement is executed when the loop has exhausted iterating the list.



```python
for num in range(10,20):     #to iterate between 10 to 20
    for i in range(2,num):    #to iterate on the factors of the number
        if num%i == 0:         #to determine the first factor
            j=num/i             #to calculate the second factor
            print ('%d equals %d * %d' % (num,i,j))
            break #to move to the next number, the #first FO
    else:                  # else part of the loop
        print (num, 'is a prime number')
   
```

    10 equals 2 * 5
    11 is a prime number
    12 equals 2 * 6
    13 is a prime number
    14 equals 2 * 7
    15 equals 3 * 5
    16 equals 2 * 8
    17 is a prime number
    18 equals 2 * 9
    19 is a prime number
    

### Additional Controls 

Loop control statements change execution from its normal sequence. When execution leaves a scope, all automatic objects that were created in that scope are destroyed.

1. **break statement** - Terminates the loop statement and transfers execution to the statement immediately following the loop.

2. **continue statement** - Causes the loop to skip the remainder of its body and immediately retest its condition prior to reiterating.

3. **pass statement** - The pass statement in Python is used when a statement is required syntactically but you do not want any command or code to execute.

#### Break Statement

It terminates the current loop and resumes execution at the next statement, just like the traditional break statement in C.


![cpp_break_statement.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1632866266632/Ma1KnnJrB.jpeg)


```python
for letter in 'Python':     # First Example
    if letter == 'h':
        break
    print ('Current Letter :', letter)

var = 10                    # Second Example
while var > 0:              
    print ('Current variable value :', var)
    var = var -1
    if var == 5:
        break

print ("Good bye!")
```

    Current Letter : P
    Current Letter : y
    Current Letter : t
    Current variable value : 10
    Current variable value : 9
    Current variable value : 8
    Current variable value : 7
    Current variable value : 6
    Good bye!
    

#### Continue Statement

It returns the control to the beginning of the while loop.. The continue statement rejects all the remaining statements in the current iteration of the loop and moves the control back to the top of the loop.


![cpp_continue_statement.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1632866276535/KZ7k4TVj3.jpeg)


```python
for letter in 'Python':     # First Example
    if letter == 'h':
        continue
    print ('Current Letter :', letter)

var = 10                    # Second Example
while var > 0:              
    
    var = var -1
    if var == 5:
        continue
    print ('Current variable value :', var)

print ("Good bye!")
```

    Current Letter : P
    Current Letter : y
    Current Letter : t
    Current Letter : o
    Current Letter : n
    Current variable value : 9
    Current variable value : 8
    Current variable value : 7
    Current variable value : 6
    Current variable value : 4
    Current variable value : 3
    Current variable value : 2
    Current variable value : 1
    Current variable value : 0
    Good bye!
    

#### Pass Statement

- It is used when a statement is required syntactically but you do not want any command or code to execute.
- The pass statement is a null operation; nothing happens when it executes. The pass is also useful in places where your code will eventually go, but has not been written yet



```python
for letter in 'Python': 
    if letter == 'h':
        pass
        print ('This is pass block')
    print ('Current Letter :', letter)

print ("Good bye!")
```

    Current Letter : P
    Current Letter : y
    Current Letter : t
    This is pass block
    Current Letter : h
    Current Letter : o
    Current Letter : n
    Good bye!
    
