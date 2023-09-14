---
title: "Introduction to Python 3"
seoTitle: "Introduction to python"
seoDescription: "Introduction to Python 3, Python Applications, Python 2x vs Python 3x"
datePublished: Tue Sep 28 2021 21:09:50 GMT+0000 (Coordinated Universal Time)
cuid: cku4kpbsf09izp9s157lb615o
slug: introduction-to-python-3
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1632863484473/7ozHqGu52.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1632863372988/f4RGcKJKm.jpeg
tags: python3, python-beginner

---

## Goals 

1. the basic knowledge you'll need to write effective Python scripts. 
2. We'll start with an introduction to the basic syntax of the Python language. 
3. I'll explain how types and values are related to objects in Python.
4. how to use Python's control statements, conditionals, loops, and functions. 
5. I'll cover Python's unique object model and how it relates to just about everything in the language. 
6. I'll cover Python's generators and decorators.
7. Finally, I'll show you Python's simple and powerful module system.

A thorough understanding of Python will help you write more efficient and effective scripts, so let's get started with Python's three essential training.



## Introduction

Python was created by Guido van Rossum during 1985- 1990.

#### GENERAL-PURPOSE:

Python is a general-purpose language which means it can be used for a wide variety of development tasks. Unlike a domain-specific language that can only be used for specific types of applications (think JavaScript and HTML/CSS for web development), a general-purpose language like Python can be used for:

- **Web applications**: Popular frameworks like the Django web application and Flask are written in Python.

- **Desktop applications**: The Dropbox client is written in Python.

- **Scientific and numeric computing**: Python is the top choice for data science and machine learning.

- **Cybersecurity**: Python is excellent for data analysis, writing system scripts that interact with an operating system, and communicating over network sockets. 

#### INTERPRETED

- Python is an interpreted language, meaning Python program code must be run using the Python interpreter.
- Traditional programming languages like C/C++ are compiled, meaning that before it can be run, the human-readable code is passed into a compiler (special program) to generate machine code — a series of bytes providing specific instructions to specific types of processors. However, Python is different. Since it’s an interpreted programming language, each line of human-readable code is passed to an interpreter that converts it to machine code at run time.
- In other words, instead of having to go through the sometimes complicated and lengthy process of compiling your code before running it, you just point the Python interpreter at your code, and you’re off!
- Part of what makes an interpreted language great is how portable it is. Compiled languages must be compiled for the specific type of computer they’re run on (i.e. think your phone vs. your laptop). For Python, as long as you’ve installed the interpreter for your computer, the exact same code will run almost anywhere!

#### High-Level

Python is a high-level language which really just means that it’s simpler and more intuitive for a human to use. Low-level languages such as C/C++ require a much more detailed understanding of how a computer works. With a high-level language, many of these details are abstracted away to make your life easier.

For instance, say you have a list of three numbers — 1, 2, and 3 — and you want to append the number 4 to that list. In C, you have to worry about how the computer uses memory, understands different types of variables (i.e., an integer vs. a string), and keeps track of what you’re doing.

Implementing this in C code is rather complicated:

```C
\\ Create list of three numbers 1,2 and 3
int *list=NULL;
int sizeList=3;
list= (int*) calloc(sizeList,sizeof(int));
if (NULL == list) { return -1 };
list[0] = 1;
list[1] = 2;
list[2] = 3;

\\ Append 4 to the list
sizeList += 1;
list = (int*) realloc(list, (size_t)(sizeList*sizeof(int)));
if (NULL == list) { return -1 };
list[3] = 4;

```

However, implementing this in Python code is much simpler:

```python
# Create a list of three numbers 1,2 and 3
list1=[1,2,3]

# Append 4 to the list
list1.append(4)

```

#### OBJECT-ORIENTED

Python is an Object-Oriented Programming (OOP) language which means that all of its elements are broken down into things called objects. A Python object is very useful for software architecture and often makes it simpler to write large, complicated applications. 

#### DYNAMIC SEMANTICS

Python uses dynamic semantics, meaning that its variables are dynamic objects. Essentially, it’s just another aspect of Python being a high-level language.

In the list example above, a low-level language like C requires you to statically define the type of a variable. So if you defined an integer x, set x = 3, and then set x = “pants”, the computer will get very confused. However, if you use Python to set x = 3, Python knows x is an integer. If you then set x = “pants”, Python knows that x is now a string.

In other words, Python lets you assign variables in a way that makes more sense to you than it does to the computer. It’s just another way that Python programming is intuitive.

It also gives you the ability to do something like creating a list where different elements have different types like the list [1, 2, “three”, “four”]. Defining that in a language like C would be a nightmare, but in Python, that’s all there is to it.

## Python Applications


Python supports cross-platform operating systems which makes building applications with it all the more convenient. Some of the globally known applications such as YouTube, BitTorrent, DropBox, etc. use Python to achieve their functionality.

1. **Web Development**: frameworks are **Django, Flask, Pyramid**. Why use a framework? The security, scalability, convenience that they provide is commendable if we compare it to starting the development of a website from scratch.


2. **Game Development**: Python is also used in the development of interactive games. There are libraries such as **PySoy which is a 3D game engine supporting Python 3**, **PyGame which provides functionality and a library for game development. Games such as Civilization-IV, Disney’s Toontown Online, Vega Strike etc**. have been built using Python.


3. **Machine Learning and Artificial Intelligence**: Machine Learning and Artificial Intelligence are the talks of the town as they yield the most promising careers for the future. We make the computer learn based on past experiences through the data stored or better yet, create algorithms which makes the computer learn by itself. The programming language that mostly everyone chooses? It’s Python. Why? Support for these domains with the libraries that exist already such as **Pandas, Scikit-Learn, NumPy and so many more**.


4. **Data Science and Data Visualization**:Data is money if you know how to extract relevant information which can help you take calculated risks and increase profits. You study the data you have, perform operations and extract the information required. Libraries such as Pandas, NumPy help you in extracting information.You can even visualize the data libraries such as **Matplotlib, Seaborn**, which are helpful in plotting graphs and much more. This is what Python offers you to become a Data Scientist.


5. **Desktop GUI**: We use Python to program desktop applications. It provides the Tkinter library that can be used to develop user interfaces. There are some other useful toolkits such as the **wxWidgets, Kivy, PYQT** that can be used to create applications on several platforms. You can start out with creating simple applications such as **Calculators, To-Do apps** and go ahead and create much more complicated applications.


6. **Web Scraping Applications**: Python is a savior when it comes to pulling a large amount of data from websites which can then be helpful in various real-world processes such as **price comparison, job listings, research, and development** and much more. 

# Python 2x vs Python 3x

Python 3 is very close to Guido's ideal vision for Python. Code written for Python 2 must be ported for use with Python 3. 

- All data types, including functions and classes, are now built on Python's object model. In Python 2, the print was a keyword, and it didn't require parentheses. 
- In Python 3 it is a function, and it does require parentheses. Python 2 had separate types for integers and long integers. Now there is just one integer type. 
- Python 2 had separate types of strings for Unicode, Ascii, and APID data. All text is now Unicode, and there's a separate APID data type.
- In Python 2, integer division returns an integer.  7/ 2 gives 3. To get the exact answer, the programmer should use 7.0 / 2. 0. In Python 3, integer division can give a float answer. 7 / 2 will give 3.5.
- In Python 2, the raw_input() function is used to get input from the user. This function reads a string.In Python 3, raw_input() function is not available.
- In Python 2, the input() function can be used to read as strings if they are inside quotes else read as numbers.	In Python 3, the input() function reads the input as a string.
