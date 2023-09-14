---
title: "Python Language Overview"
seoTitle: "Python Language Overview"
seoDescription: "Python Language Overview, Hello World in Python, Python Anatomy, Statement & Expression, Whitespace & comments, Using print(), Block and Scope, conditionals"
datePublished: Tue Sep 28 2021 21:20:39 GMT+0000 (Coordinated Universal Time)
cuid: cku4l38gq09mqrps1e2xk1fbe
slug: python-language-overview
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1632863806332/H1J_eo5qZ.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1632863873699/-AsILLLXr.jpeg
tags: python3, python-beginner

---

This topic covers Bird's-eye view of the language as a whole. We'll use examples to describe different elements of Python's syntax without getting into much detail about how each feature works. The idea is for you to become familiar with the syntax of the language so that you may better learn its features later. 

Few keypoints: 

- Python does not look like a lot of other languages. It doesn't use braces or semicolons, line endings and indentation are meaningful.
- In Python, everything is an object. 

## Hello World

The Hello World program is a traditional first step in learning a new language, but it's actually more than that. The purpose of Hello World is to validate your development environment. Whenever you set up a new development environment, it's a good idea to use a simple, minimal, and functional program to confirm that your development cycle functions as you expect, and that's what Hello World is for. 


```python
print("Hello World")
```

    Hello World
    


```python
print("Hi, I am learning Python!!")
```

    Hi, I am learning Python!!
    

## Python Anatomy


```python
from datetime import datetime

def print_date():
    date=datetime.today()
    print(date)

if __name__=="__main__":
    print_date()
```

    2021-09-19 16:06:22.352907
    

- the first line in the script is an **import statement**. This tells the Python interpreter to import a module from the library. The module may contain any combination of classes, functions, or other Python objects. In this case, it's importing the datetime module, which is used to display the current datetime . There are standard library modules or you may define your own. A Python script may have multiple import statements or you may specify multiple modules in one import statement. After the import statements, you find the rest of the script. 
- then we have a function definition as **def func()** which holds the information about what this function does, In this case this function prints the current date time. 
- then we have **if __name__=="__main__"**, The condition **if __name__ == "__main__"** is used in a Python program to execute the code inside the if statement only when the program is executed directly by the Python interpreter. When the code in the file is imported as a module the code inside the if statement is not executed.

## Statement and Expression

- The distinction between statements and expressions is a bit different in every computer language. Generally speaking, a statement is a unit of execution, and an expression is a unit of evaluation.
-  In Python, an expression is any combination of literals, identifiers, and operators. Generally, this means anything that returns a value is an expression. 


```python
# expressions

x=5
y=10

def z(x,y):
    return y/x

print(x+y) # addition operation, hence it will return a value
print(x*y) # multiplication operation, hence it will return a value
print(True) # built-in constant value  
print((x,y)) # tuple 
print(z(x,y)) # function call
```

    15
    50
    True
    (5, 10)
    2
    

-  A statement is a line of code. It may be an expression, or it may be something like the import statement or a break or a continue.
-  In Python, a statement is a line of code. It does not require a semicolon at the end of the line. And so this import statement is a statement. This assignment, even though it's also an expression, is a statement because it's a line of code by itself. And then this print function, of course, is also a statement, and it's also an expression because, even though we're not using the returned value from the function call, it still does return a value. Now, in most cases, you'll see one statement per line. 
- Although you may put more than one statement in the single line using a semicolon.


```python
print("this is statement one!"); print("this is statement two!!")
```

    this is statement one!
    this is statement two!!
    

## Whitespace and comments

Unlike most other modern scripting languages, whitespace is significant in Python. There's no brackets or parentheses to match up just indents.

for example in C block or scope of a function is determined using braces: 

```
function main()
{
    printf("the is an example in c language");
}
```

whereas, In python there is no brackets or braces to determine. Indentation determine the block and scope of a function


```python
# example 1
import platform

def main(): # Block started for function main()
    message() # statement inside function main() block

def message(): # Block started for function message()
    print('This is python version {}'.format(platform.python_version())) # statement inside function message() block
    
if __name__ == '__main__': main()
```

    This is python version 3.7.4
    


```python
# example 2
import platform

def main(): # Block started for function main()
    message() # statement inside function main() block

def message(): # Block started for function message()
    print('This is python version {}'.format(platform.python_version())) # statement inside function message() block
    print("statement 2")
    print("statement 3")
if __name__ == '__main__': main()
```

    This is python version 3.7.4
    statement 2
    statement 3
    


```python
# example 3
import platform

def main(): # Block started for function main()
    message() # statement inside function main() block

def message(): # Block started for function message()
    print('This is python version {}'.format(platform.python_version())) # statement inside function message() block
    print("statement 2")
print("statement 3")
if __name__ == '__main__': main()
```

    statement 3
    This is python version 3.7.4
    statement 2
    


```python
# example 4
import platform

def main(): # Block started for function main()
    message() # statement inside function main() block

def message(): # Block started for function message()
    print('This is python version {}'.format(platform.python_version())) # statement inside function message() block
    if True:
        print("statement 2") # block of if 
    else:
        print("statement 3") # block of else
        
if __name__ == '__main__': main()
```

    This is python version 3.7.4
    statement 2
    

#### Comments

In python, Comments are introduced by pound sign (#), there is nothing like mutli-line comments in python. But **Docstring** can be used as comments where you can define the functionality or give description about the block or function.

**DocString** : Triple double coat (""") and single coat (''') 


```python
# this is comment
```


```python
def add(x,y):
    z=x+y # addition of two variable x & y and assignment of the sum in z variable
    print(z) # printing the result
    
add(5,10)
    
```

    15
    


```python
"""
Author: xyz
Description:
Writes the words Hello World on the screen

"""

def print_msg():
    print("hello world!!")
    sub(10,5)
    
    

def sub(x,y):
    '''
    Author: abc
    Description:
    Writes result of x-y on the screen
    '''
    print(x-y)
    
print_msg()

```

    hello world!!
    5
    

## Using print()

In earlier version of python, i.e python 2, Print was not a function and strings were not an object
for ex: 
```python
    print "hello world!!
    age = 5
    print "I am bob, and i am %d years old" % age
```

but in python 3, same code can be written as:


```python
# example 1
print ("Hello World!!")

# example 2
age =5 
print("I am Bob, I am {} years old".format(age))

# example 3 
print(f"I am Bob, I am {age} years old")

#example 4
print("this is a string 1","this is string 2")

#example 5
x,y=5,10
print(x,y)


```

    Hello World!!
    I am Bob, I am 5 years old
    I am Bob, I am 5 years old
    this is a string 1 this is string 2
    5 10
    

## Block and Scope

 Python differs from many languages in how blocks are delimited. Python does not use brackets or any special characters for blocks, instead it uses indentation.
 
- if x is less than y, and indented below that is this print statement. So that indent means that it's a block and it's associated with the control above it


```python
# block example

x = 42 
y= 73

if x < y:
    print('x < y: x is {} and y is {}'.format(x,y))
    
```

    x < y: x is 42 and y is 73
    


```python
# example 2

x =10 
y = 5 
if x < y:
    print('x < y: x is {} and y is {}'.format(x,y))
print("something else!!")
```

    something else!!
    


```python
# example 2

x =10 
y = 5 
if x < y:
    print('x < y: x is {} and y is {}'.format(x,y))
    print("line 2")
    print("line 3")
    print("line 4")
  print("line 5")
    

```


      File "<tokenize>", line 10
        print("line 5")
        ^
    IndentationError: unindent does not match any outer indentation level
    



```python
x =10 
y = 5 
if x > y:
    print('x < y: x is {} and y is {}'.format(x,y))
    print("line 2")
    print("line 3")
    
    
    print("line 4")
    print("line 5")
```

    x < y: x is 10 and y is 5
    line 2
    line 3
    line 4
    line 5
    

Note: Blocks do not define scope in Python. Functions, objects, and modules do define scope in Python.
for ex: 


```python
# example block doesn't define the scope of a variable 
x =10 
y = 5 
if x > y:
    z= 100
    print('x < y: x is {} and y is {}'.format(x,y))

print("z is {}".format(z))
```

    x < y: x is 10 and y is 5
    z is 100
    


```python
# example function can define the scope of a variable


def sqr():
    x=10**2
    
sqr()

print(x)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-2-4731039992ca> in <module>
          7 sqr()
          8 
    ----> 9 print(x)
    

    NameError: name 'x' is not defined


## Conditionals

Conditional Statement in Python perform different computations or actions depending on whether a specific Boolean constraint evaluates to true or false. Conditional statements are handled by IF statements in Python.


```python
# example if-else
x=7

if x%2==0: # condition if x is fully divisible by 2 i.e remainder = 0 then print it's EVEN else print it's ODD
    print("X is even")
else:
    print("X is odd")
```

    X is odd
    


```python
# example if-elif-else

x=10
y=20

if x<y:
    print("X is less than Y")
elif x>y:
    print("X is greater than Y")
else:
    print("X & Y are equal")
    
    
```

    X is less than Y
    


```python
# nested if else
import random 

day=random.randint(0, 6)
if day==0:
    print("it's Monday")
elif day==1:
    print("it's Tuesday")
elif day==2:
    print("it's Wednesday")
elif day==3:
    print("it's Thursday")
elif day==4:
    print("it's Friday")
elif day==5:
    print("it's Saturday")
elif day==6:
    print("it's Sunday")

```

    it's Wednesday
    

## Loops

Python provides two basic types of loops.

#### While Loop
 A while loop tests a conditional expression and the body of the loop is executed while the condition remains true.

![whileLoopFlowchart.webp](attachment:whileLoopFlowchart.webp)

#### For Loop

 A for loop iterates over a sequence and the body of the loop is executed for each element of the sequence and until the sequence is exhausted.

![forLoop.webp](attachment:forLoop.webp)



#### Example of loops


```python
# while loop

n=0
words =['one','two','three','four','five']

while(n<5): # execute utill n = 5
    print(words[n], end=' ')
    n+=1
    
```

    one two three four five 


```python
# fibonacci series in while loop
# F 0 = 0, F 1 = 1, and then using the recursive formula F n = F n-1 + F n-2 to get the rest.

a,b=0,1
while b< 1000:
    print(b , end=' ')
    a,b=b,a+b
```

    1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987 


```python
# for loop
words =['one','two','three','four','five']

for i in words:
    print(i, end= " ")
```

    one two three four five 

## Functions

Functions in Python serve the purpose of both functions and subroutines in other languages.

Python Functions is a block of related statements designed to perform a computational, logical, or evaluative task. The idea is to put some commonly or repeatedly done tasks together and make a function so that instead of writing the same code again and again for different inputs, we can do the function calls to reuse code contained in it over and over again. 

Functions can be both built-in or user-defined. It helps the program to be concise, non-repetitive, and organized.

syntax:

```python
def function_name(parameters):
    """docstring"""
    statement(s)
    return expression
```


```python
# example simple working of a function

def func(n):
    print(n)

func(40)

```

    40
    


```python
# example with default parameter
def func(n=1):
    print(n)

func()
```

    1
    


```python
# example function always return a value
def func(n=1):
    print(n)

x= func()
print(x)
```

    1
    None
    

## Objects

Class is a definition and object is an instance of a class. **self** represent reference to an object when class is used to create an object. we use the **dot** as the de-reference operator to reference members of the object.


```python
class Duck: # class definition
    
    sound="Quaack!" #class variable or property
    walks="walks like a duck" #class variable or property
    
    def quack(self): #class method
        print(self.sound)
        
    def walk(self): # class method
        print(self.walks)

def main():
    donald= Duck() # creating an object
    donald.quack() # calling class method quack using object
    donald.walk() # calling class method  walk using object

if __name__ == "__main__": main()
```

    Quaack!
    walks like a duck
    
