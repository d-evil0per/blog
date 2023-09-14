---
title: "Functions in Python"
seoTitle: "Functions in Python"
seoDescription: "Defining a Function, Calling a Function, Function Arguments,  Pass by reference vs value, The Anonymous Functions, Generators & Decorators in Python"
datePublished: Tue Sep 28 2021 22:05:14 GMT+0000 (Coordinated Universal Time)
cuid: cku4mokh809ufrps16srg9vp1
slug: functions-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1632866578551/rwDw_v2gU.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1632866603533/o37sm2ryB.png
tags: python, python-beginner

---

## Defining a Function


You can define functions to provide the required functionality. Here are simple rules to define a function in Python.

- Function blocks begin with the keyword def followed by the function name and parentheses ( ( ) ).

- Any input parameters or arguments should be placed within these parentheses. You can also define parameters inside these parentheses.

- The first statement of a function can be an optional statement - the documentation string of the function or docstring.

- The code block within every function starts with a colon (:) and is indented.

- The statement return [expression] exits a function, optionally passing back an expression to the caller. A return statement with no arguments is the same as return None.

**Syntax**

```Python
def functionname( parameters ):
   "function_docstring"
   function_suite
   return [expression]
```


```python
def printme( str ):
    "This prints a passed string into this function"
    print( str)
    return

printme("Hello World!!")
```

    Hello World!!
    

## Calling a Function

Defining a function only gives it a name, specifies the parameters that are to be included in the function and structures the blocks of code.
Once the basic structure of a function is finalized, you can execute it by calling it from another function or directly from the Python prompt.


```python
# Now you can call printme function
printme("I'm first call to user defined function!")
printme("Again second call to the same function")
```

    I'm first call to user defined function!
    Again second call to the same function
    

## Function Arguments

You can call a function by using the following types of formal arguments −

- Required arguments
- Keyword arguments
- Default arguments
- Variable-length arguments

#### Required arguments

Required arguments are the arguments passed to a function in correct positional order. Here, the number of arguments in the function call should match exactly with the function definition.


```python
def printme( str ):
    "This prints a passed string into this function"
    print (str)
    return

# Now you can call printme function
printme()
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-6-df004a0b2340> in <module>
          5 
          6 # Now you can call printme function
    ----> 7 printme()
    

    TypeError: printme() missing 1 required positional argument: 'str'


#### Keyword arguments

Keyword arguments are related to the function calls. When you use keyword arguments in a function call, the caller identifies the arguments by the parameter name.


```python
# Function definition is here
def printme( str ):
    "This prints a passed string into this function"
    print( str)
    return

# Now you can call printme function
printme( str = "My string")
```

    My string
    


```python
# Function definition is here
def printinfo( name, age ):
    "This prints a passed info into this function"
    print ("Name: ", name)
    print ("Age ", age)
    return

# Now you can call printinfo function
printinfo( age=50, name="miki" )
```

    Name:  miki
    Age  50
    

#### Default arguments

A default argument is an argument that assumes a default value if a value is not provided in the function call for that argument. The following example gives an idea on default arguments, it prints default age if it is not passed −


```python
# Function definition is here
def printinfo( name, age = 35 ):
    "This prints a passed info into this function"
    print ("Name: ", name)
    print ("Age ", age)
    return

# Now you can call printinfo function
printinfo( age=50, name="miki" )
printinfo( name="miki" )

```

    Name:  miki
    Age  50
    Name:  miki
    Age  35
    Name:  23
    Age  mikki
    

#### Variable-length arguments

You may need to process a function for more arguments than you specified while defining the function. These arguments are called variable-length arguments and are not named in the function definition, unlike required and default arguments.

Syntax for a function with non-keyword variable arguments is this −
```Python
def functionname([formal_args,] *var_args_tuple ):
   "function_docstring"
   function_suite
   return [expression]
```


```python
# Function definition is here
def printinfo( arg1, *vartuple ):
    "This prints a variable passed arguments"
    print ("Output is: ")
    print (arg1)
    for var in vartuple:
        print (var)
    return

# Now you can call printinfo function
printinfo( 10 )
printinfo( 70, 60, 50 )
```

    Output is: 
    10
    Output is: 
    70
    60
    50
    


```python
def kitten(**kwargs):
    if len(kwargs):
        for k in kwargs:
            print(f" Kitten {k} says {kwargs[k]}")
    else:
        print("meow!!")
        
kitten(alice ="grrrrr", angel="purrrr")
```

     Kitten alice says grrrrr
     Kitten angel says purrrr
    

## The return Statement
The statement return [expression] exits a function, optionally passing back an expression to the caller. A return statement with no arguments is the same as return None


```python
# Function definition is here
def sum( arg1, arg2 ):
    # Add both the parameters and return them."
    total = arg1 + arg2
    print( "Inside the function : ", total)
    return total

# Now you can call sum function
total = sum( 10, 20 )
print ("Outside the function : ", total )
```

    Inside the function :  30
    Outside the function :  30
    

## Pass by reference vs value
All parameters (arguments) in the Python language are passed by reference. It means if you change what a parameter refers to within a function, the change also reflects back in the calling function. For example −


```python
# Function definition is here
def changeme( mylist ):
    "This changes a passed list into this function"
    mylist.append([1,2,3,4])
    print ("Values inside the function: ", mylist)
    return

# Now you can call changeme function
mylist = [10,20,30]
changeme( mylist )
print ("Values outside the function: ", mylist)
```

    Values inside the function:  [10, 20, 30, [1, 2, 3, 4]]
    Values outside the function:  [10, 20, 30, [1, 2, 3, 4]]
    

## The Anonymous Functions

These functions are called anonymous because they are not declared in the standard manner by using the def keyword. You can use the lambda keyword to create small anonymous functions.

- Lambda forms can take any number of arguments but return just one value in the form of an expression. They cannot contain commands or multiple expressions.

- An anonymous function cannot be a direct call to print because lambda requires an expression

- Lambda functions have their own local namespace and cannot access variables other than those in their parameter list and those in the global namespace.

- Although it appears that lambda's are a one-line version of a function, they are not equivalent to inline statements in C or C++, whose purpose is by passing function stack allocation during invocation for performance reasons.

**Syntax**

The syntax of lambda functions contains only a single statement, which is as follows −
```Python
lambda [arg1 [,arg2,.....argn]]:expression
```


```python
# Function definition is here
sum = lambda arg1, arg2: arg1 + arg2;

# Now you can call sum as a function
print ("Value of total : ", sum( 10, 20 ))
print ("Value of total : ", sum( 20, 20 ))
```

    Value of total :  30
    Value of total :  40
    

Learn more on [Python lambda function](https://www.guru99.com/python-lambda-function.html#:~:text=Summary%201%20Lambdas%2C%20also%20known%20as%20anonymous%20functions%2C,lambda%20is%3A%20lambda%20parameter%3A%20expression%20More%20items...%20)

## Generators in Python

There are two terms involved when we discuss generators.

- **Generator-Function** : A generator-function is defined like a normal function, but whenever it needs to generate a value, it does so with the yield keyword rather than return. If the body of a def contains yield, the function automatically becomes a generator function.


```python
# A generator function that yields 1 for first time,
# 2 second time and 3 third time
def simpleGeneratorFun():
    for i in range(0,5):
        yield i

# Driver code to check above generator function
for value in simpleGeneratorFun():
    print(value)

```

    0
    1
    2
    3
    4
    

- **Generator-Object** : Generator functions return a generator object. Generator objects are used either by calling the next method on the generator object or using the generator object in a “for in” loop (as shown in the above program).


```python
# A Python program to demonstrate use of
# generator object with next()

# A generator function
def simpleGeneratorFun():
    for i in range(0,5):
        yield i

# x is a generator object
x = simpleGeneratorFun()

# Iterating over the generator object using next
print(x.__next__()) # In Python 3, __next__()
print(x.__next__())
print(x.__next__())

```

    0
    1
    2
    


```python
# A simple generator for Fibonacci Numbers
def fib(limit):

    # Initialize first two Fibonacci Numbers
    a, b = 0, 1

    # One by one yield next Fibonacci Number
    while a < limit:
        yield a
        a, b = b, a + b

# Create a generator object
x = fib(5)

# Iterating over the generator object using next
print(x.__next__()) # In Python 3, __next__()
print(x.__next__())
print(x.__next__())
print(x.__next__())
print(x.__next__())
# print(x.__next__())

# Iterating over the generator object using for
# in loop.
print("\nUsing for in loop")
for i in fib(5):
    print(i)

```

    0
    1
    1
    2
    3
    
    Using for in loop
    0
    1
    1
    2
    3
    


```python
iter_list = iter(['Geeks', 'For', 'Geeks'])
for i in iter_list:
    print(i)

```

    Geeks
    For
    Geeks
    

## Decorators in Python

Decorators are a very powerful and useful tool in Python since it allows programmers to modify the behaviour of function or class. Decorators allow us to wrap another function in order to extend the behaviour of the wrapped function, without permanently modifying it. 

**Syntax for Decorator:** 
 ```python
@gfg_decorator
def hello_decorator():
    print("Gfg")

'''Above code is equivalent to -

def hello_decorator():
    print("Gfg")
    
hello_decorator = gfg_decorator(hello_decorator)'''

```


```python
# defining a decorator
def hello_decorator(func):

	# inner1 is a Wrapper function in
	# which the argument is called
	
	# inner function can access the outer local
	# functions like in this case "func"
	def inner1():
		print("Hello, this is before function execution")

		# calling the actual function now
		# inside the wrapper function.
		func()

		print("This is after function execution")
		
	return inner1


# defining a function, to be called inside wrapper
def function_to_be_used():
	print("This is inside the function !!")


# passing 'function_to_be_used' inside the
# decorator to control its behavior
function_to_be_used = hello_decorator(function_to_be_used)


# calling the function
function_to_be_used()

```

    Hello, this is before function execution
    This is inside the function !!
    This is after function execution
    


```python

@hello_decorator
def function_to_be_used():
	print("This is inside the function !!")
    
function_to_be_used()
```

    Hello, this is before function execution
    This is inside the function !!
    This is after function execution
    


```python
def pattern_wrapper(func):
    def inner(*args, **kwargs):
        print("-"*23)
        print("| ",end="")
        func(*args, **kwargs)
        print(" |")
        print("-"*23)
    return inner
    
@pattern_wrapper
def sumOfEven(List):
    sum=0
    for num in List:
        if num%2 == 0:
            sum=sum+num
        else:
            continue
    else:
        print(f"Sum of evens are {sum}",end="")
        
@pattern_wrapper       
def sumOfOdd(List):
    sum=0
    for num in List:
        if num%2 != 0:
            sum=sum+num
        else:
            continue
    else:
        print(f"Sum of odds are {sum}",end="")
            
def main():
    List=[1,2,3,4,5,6,7,8,9]
    sumOfEven(List)
    sumOfOdd(List)
main()
```

    -----------------------
    | Sum of evens are 20 |
    -----------------------
    -----------------------
    | Sum of odds are 25 |
    -----------------------
    


```python
import time

def execution_time(f):
    def wrapper():
        t1=time.time()
        f()
        t2=time.time()
        print(f"Execution Time: {(t2-t1) * 1000} ms")
    return wrapper
    
@execution_time
def big_sum():
    num_list=[]
    for num in range(0,100000):
        num_list.append(num)
    i=0
    total=0
    while i < len(num_list):
        total = total + num_list[i]
        i = i + 1
    print(f"Big sum : {total}")

big_sum()
```

    Big sum : 4999950000
    Execution Time: 27.924060821533203 ms
    
