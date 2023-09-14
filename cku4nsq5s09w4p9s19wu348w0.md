---
title: "Python Exception Handling"
seoTitle: "Python Exception Handling"
seoDescription: "Difference between Syntax Error and Exceptions, Try and Except Statement – Catching Exceptions, Raising Exception, Built-in Exceptions in Python"
datePublished: Tue Sep 28 2021 22:36:28 GMT+0000 (Coordinated Universal Time)
cuid: cku4nsq5s09w4p9s19wu348w0
slug: python-exception-handling
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1632868475994/3bUbw52G5.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1632868495900/4uPjkgEId.png
tags: python, python-beginner

---

Error in Python can be of two types i.e. Syntax errors and Exceptions. Errors are the problems in a program due to which the program will stop the execution. On the other hand, exceptions are raised when some internal events occur which changes the normal flow of the program. 

**Difference between Syntax Error and Exceptions**

- **Syntax Error**: As the name suggests this error is caused by the wrong syntax in the code. It leads to the termination of the program


```python
# initialize the amount variable
amount = 10000

# check that You are eligible to
# purchase Dsa Self Paced or not
if(amount > 2999)
print("You are eligible to purchase Dsa Self Paced")

```


      File "<ipython-input-1-8d94ddc68478>", line 6
        if(amount > 2999)
                         ^
    SyntaxError: invalid syntax
    


- **Exceptions**: Exceptions are raised when the program is syntactically correct, but the code resulted in an error. This error does not stop the execution of the program, however, it changes the normal flow of the program.


```python
# initialize the amount variable
marks = 10000

# perform division with 0
a = marks / 0
print(a)

```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-2-5f312778a383> in <module>
          3 
          4 # perform division with 0
    ----> 5 a = marks / 0
          6 print(a)
    

    ZeroDivisionError: division by zero


### Try and Except Statement – Catching Exceptions

Try and except statements are used to catch and handle exceptions in Python. Statements that can raise exceptions are kept inside the try clause and the statements that handle the exception are written inside except clause.

**Example**: Let us try to access the array element whose index is out of bound and handle the corresponding exception.


```python
# Python program to handle simple runtime error
#Python 3

a = [1, 2, 3]
try:
    print ("Second element = %d" %(a[1]))

    # Throws error since there are only 3 elements in array
    print ("Fourth element = %d" %(a[3]))

except:
    print ("An error occurred")

```

    Second element = 2
    An error occurred
    

### Catching Specific Exception
A try statement can have more than one except clause, to specify handlers for different exceptions. Please note that at most one handler will be executed. For example, we can add IndexError in the above code. The general syntax for adding specific exceptions are – 
```Python
try:
    # statement(s)
except IndexError:
    # statement(s)
except ValueError:
    # statement(s)
```


```python
# Program to handle multiple errors with one
# except statement
# Python 3

def fun(a):
    if a < 4:

        # throws ZeroDivisionError for a = 3
        b = a/(a-3)

    # throws NameError if a >= 4
    print("Value of b = ", b)

try:
    fun(3)
    fun(5)

# note that braces () are necessary here for
# multiple exceptions
except ZeroDivisionError:
    print("ZeroDivisionError Occurred and Handled")
except NameError:
    print("NameError Occurred and Handled")

```

    NameError Occurred and Handled
    

### Try with Else Clause
In python, you can also use the else clause on the try-except block which must be present after all the except clauses. The code enters the else block only if the try clause does not raise an exception.


```python
# Program to depict else clause with try-except
# Python 3
# Function which returns a/b
def AbyB(a , b):
    try:
        c = ((a+b) / (a-b))
    except ZeroDivisionError:
        print ("a/b result in 0")
    else:
        print (c)

# Driver program to test above function
AbyB(2.0, 3.0)
AbyB(3.0, 3.0)

```

    -5.0
    a/b result in 0
    

### Finally Keyword in Python
Python provides a keyword finally, which is always executed after the try and except blocks. The finally block always executes after normal termination of try block or after try block terminates due to some exception.

Syntax:
```Python
try:
    # Some Code.... 

except:
    # optional block
    # Handling of exception (if required)

else:
    # execute if no exception

finally:
    # Some code .....(always executed)
    
```


```python
# Python program to demonstrate finally

# No exception Exception raised in try block
try:
    k = 5//0 # raises divide by zero exception.
    print(k)

# handles zerodivision exception
except ZeroDivisionError:
    print("Can't divide by zero")

finally:
    # this block is always executed
    # regardless of exception generation.
    print('This is always executed')

```

    Can't divide by zero
    This is always executed
    

### Raising Exception
The raise statement allows the programmer to force a specific exception to occur. The sole argument in raise indicates the exception to be raised. This must be either an exception instance or an exception class (a class that derives from Exception).




```python
# Program to depict Raising Exception

try:
    raise NameError("Hi there") # Raise Error
except NameError:
    print ("An exception")
    raise # To determine whether the exception was raised or not

```

    An exception
    


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-10-23e59b0f9c23> in <module>
          2 
          3 try:
    ----> 4     raise NameError("Hi there") # Raise Error
          5 except NameError:
          6     print ("An exception")
    

    NameError: Hi there


### Built-in Exceptions in Python

- **AssertionError** :	Raised when an assert statement fails.
- **AttributeError** :	Raised when attribute assignment or reference fails.
- **EOFError** :	Raised when the input() function hits end-of-file condition.
- **FloatingPointError**:	Raised when a floating point operation fails.
- **GeneratorExit**:	Raise when a generator's close() method is called.
- **ImportError**:	Raised when the imported module is not found.
- **IndexError**:	Raised when the index of a sequence is out of range.
- **KeyError**:	Raised when a key is not found in a dictionary.
- **KeyboardInterrupt**:	Raised when the user hits the interrupt key (Ctrl+C or Delete).
- **MemoryError**:	Raised when an operation runs out of memory.
- **NameError**:	Raised when a variable is not found in local or global scope.
- **NotImplementedError**:	Raised by abstract methods.
- **OSError**:	Raised when system operation causes system related error.
- **OverflowError**:	Raised when the result of an arithmetic operation is too large to be represented.
- **ReferenceError**:	Raised when a weak reference proxy is used to access a garbage collected referent.
- **RuntimeError**:	Raised when an error does not fall under any other category.
- **StopIteration**:	Raised by next() function to indicate that there is no further item to be returned by iterator.
- **SyntaxError**:	Raised by parser when syntax error is encountered.
- **IndentationError**:	Raised when there is incorrect indentation.
- **TabError**:	Raised when indentation consists of inconsistent tabs and spaces.
- **SystemError**:	Raised when interpreter detects internal error.
- **SystemExit**:	Raised by sys.exit() function.
- **TypeError**:	Raised when a function or operation is applied to an object of incorrect type.
- **UnboundLocalError**:	Raised when a reference is made to a local variable in a function or method, but no value has been bound to that variable.
- **UnicodeError**:	Raised when a Unicode-related encoding or decoding error occurs.
- **UnicodeEncodeError**:	Raised when a Unicode-related error occurs during encoding.
- **UnicodeDecodeError**:	Raised when a Unicode-related error occurs during decoding.
- **UnicodeTranslateError**:	Raised when a Unicode-related error occurs during translating.
- **ValueError**:	Raised when a function gets an argument of correct type but improper value.
- **ZeroDivisionError**:	Raised when the second operand of division or modulo operation is zero.
