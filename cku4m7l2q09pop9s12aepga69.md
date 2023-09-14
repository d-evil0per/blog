---
title: "Operators in Python"
seoTitle: "Operators in Python"
seoDescription: "Arithmetic Operators, Bitwise Operators, Operator Precedence"
datePublished: Tue Sep 28 2021 21:52:02 GMT+0000 (Coordinated Universal Time)
cuid: cku4m7l2q09pop9s12aepga69
slug: operators-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1632865669528/6aVZ4rBIY.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1632865881348/IV8Tz6Bu4.png
tags: python, python-beginner

---

Python Operators in general are used to perform operations on values and variables. These are standard symbols used for the purpose of logical and arithmetic operations. In this article, we will look into different types of Python operators.

#### Arithmetic Operators

Arithmetic operators are used to performing mathematical operations like addition, subtraction, multiplication, and division.


![Arthmetic operators.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632865686268/EQxJydfhei.png)


```python
# Examples of Arithmetic Operator
a = 9
b = 4

# Addition of numbers
add = a + b

# Subtraction of numbers
sub = a - b

# Multiplication of number
mul = a * b

# Division(float) of number
div1 = a / b

# Division(floor) of number
div2 = a // b

# Modulo of both number
mod = a % b

# Power
p = a ** b

# print results
print(add)
print(sub)
print(mul)
print(div1)
print(div2)
print(mod)
print(p)

```

    13
    5
    36
    2.25
    2
    1
    6561
    

#### Bitwise Operators

Bitwise operators act on bits and perform the bit-by-bit operations. These are used to operate on binary numbers.

![bitwise operators.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632865701145/A6J_IyEEq.png)


```python
# Examples of Bitwise operators
a = 10
b = 4

# Print bitwise AND operation
"""
a = 00001010
b = 00000100
 ------------
    00000000 = 0
    
"""
print(a & b)

# Print bitwise OR operation
"""
a = 00001010
b = 00000100
 ------------
    00001110 = 14
"""
print(a | b)

# Print bitwise NOT operation
"""
a            =  00001010 =10
~a           =  11110101 = -11
or -10-1=-11
"""
print(~a)

# print bitwise XOR operation
"""
a=   00001010
b=   00000100
------------------
xor= 00001110 = 14

"""
print(a ^ b) 

# print bitwise right shift operation
print(a >> 2) #00001010 >>2 => 00000101 => 00000010 =2

# print bitwise left shift operation
print(a << 2) #00001010 <<2 => 00010100 => 00101000 =40

```

    0
    14
    -11
    14
    2
    40
    

## Operator Precedence

Till now you would have come across many operators like addition, multiplication, etc. But what will you do when you have multiple operators in one expression?

This is the situation where we use the precedence of the operators, to get the correct result.


![Opeartor-precedence.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1632865827039/0I4ouHzCb.jpeg)

**Operator precedence Table in Python:**

![operator precedence.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632865842261/oom0Kwf0K.png)

**PEMDAS Rule in Python:**
We would have learned of the BODMAS rule in mathematics while giving preference to the operators. We have a similar rule in Python and that is PEMDAS. Where,

- **P** means parentheses
- **E** means exponent
- **M** means multiplication
- **D** means division
- **A** means addition
- **S** means Subtraction


```python
a = 20
b = 10
c = 15
d = 5
e = 0

e = (a + b) * c / d       #( 30 * 15 ) / 5
print ("Value of (a + b) * c / d is ",  e)

e = ((a + b) * c) / d     # (30 * 15 ) / 5
print ("Value of ((a + b) * c) / d is ",  e)

e = (a + b) * (c / d);    # (30) * (15/5)
print ("Value of (a + b) * (c / d) is ",  e)

e = a + (b * c) / d;      #  20 + (150/5)
print ("Value of a + (b * c) / d is ",  e)
```

    Value of (a + b) * c / d is  90.0
    Value of ((a + b) * c) / d is  90.0
    Value of (a + b) * (c / d) is  90.0
    Value of a + (b * c) / d is  50.0
    
