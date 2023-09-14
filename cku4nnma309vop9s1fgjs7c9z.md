---
title: "OOPs Concept in Python"
seoTitle: "OOPs Concept in Python"
seoDescription: "Class, Class Objects, Constructors, Destructors, Inheritance, Encapsulation, Polymorphism, Abstract Class"
datePublished: Tue Sep 28 2021 22:32:29 GMT+0000 (Coordinated Universal Time)
cuid: cku4nnma309vop9s1fgjs7c9z
slug: oops-concept-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1632868240885/sKaGpLJFw.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1632868261362/fiiGnjXVV.png
tags: python, python-beginner

---


### Class
Class creates a user-defined data structure, which holds its own data members and member functions, which can be accessed and used by creating an instance of that class. A class is like a blueprint for an object.

Some points on Python class:  

- Classes are created by keyword class.
- Attributes are the variables that belong to a class.
- Attributes are always public and can be accessed using the dot (.) operator. Eg.: Myclass.Myattribute

**Class Definition Syntax:**
```Python
class ClassName:
    # Statement-1
    .
    .
    .
    # Statement-N
```

### Class Objects
An Object is an instance of a Class. A class is like a blueprint while an instance is a copy of the class with actual values. It’s not an idea anymore, it’s an actual dog, like a dog of breed pug who’s seven years old. You can have many dogs to create many different instances, but without the class as a guide, you would be lost, not knowing what information is required.
An object consists of : 

- **State**: It is represented by the attributes of an object. It also reflects the properties of an object.
- **Behavior**: It is represented by the methods of an object. It also reflects the response of an object to other objects.
- **Identity**: It gives a unique name to an object and enables one object to interact with other objects.


![Blank-Diagram-Page-1-5.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632868080046/p_umKbiqC.png)

### Declaring Objects (Also called instantiating a class)
When an object of a class is created, the class is said to be instantiated. All the instances share the attributes and the behavior of the class. But the values of those attributes, i.e. the state are unique for each object. A single class may have any number of instances.

Example:


![Blank-Diagram-Page-1-3.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632868091720/blDBUqudQ.png)



```python
# Python3 program to
# demonstrate instantiating
# a class


class Dog:

    # A simple class
    # attribute
    attr1 = "mammal"
    attr2 = "dog"

    # A sample method
    def fun(self):
        print("I'm a", self.attr1)
        print("I'm a", self.attr2)

# Driver code
# Object instantiation
Rodger = Dog()

# Accessing class attributes
# and method through objects
print(Rodger.attr1)
Rodger.fun()

```

    mammal
    I'm a mammal
    I'm a dog
    

### The self
Class methods must have an extra first parameter in the method definition. We do not give a value for this parameter when we call the method, Python provides it.
If we have a method that takes no arguments, then we still have to have one argument.
This is similar to this pointer in C++ and this reference in Java.
When we call a method of this object as myobject.method(arg1, arg2), this is automatically converted by Python into MyClass.method(myobject, arg1, arg2) – this is all the special self is about.

### __init__ method
The __init__ method is similar to constructors in C++ and Java. Constructors are used to initializing the object’s state. Like methods, a constructor also contains a collection of statements(i.e. instructions) that are executed at the time of Object creation. It runs as soon as an object of a class is instantiated. The method is useful to do any initialization you want to do with your object.

### Class and Instance Variables
Instance variables are for data, unique to each instance and class variables are for attributes and methods shared by all instances of the class. Instance variables are variables whose value is assigned inside a constructor or method with self whereas class variables are variables whose value is assigned in the class.

Defining instance variable using a constructor. 


```python
# Python3 program to show that the variables with a value
# assigned in the class declaration, are class variables and
# variables inside methods and constructors are instance
# variables.

# Class for Dog
class Dog:

    # Class Variable
    animal = 'dog'

    # The init method or constructor
    def __init__(self, breed, color):

        # Instance Variable	
        self.breed = breed
        self.color = color

# Objects of Dog class
Rodger = Dog("Pug", "brown")
Buzo = Dog("Bulldog", "black")

print('Rodger details:')
print('Rodger is a', Rodger.animal)
print('Breed: ', Rodger.breed)
print('Color: ', Rodger.color)

print('\nBuzo details:')
print('Buzo is a', Buzo.animal)
print('Breed: ', Buzo.breed)
print('Color: ', Buzo.color)

# Class variables can be accessed using class
# name also
print("\nAccessing class variable using class name")
print(Dog.animal)

```

    Rodger details:
    Rodger is a dog
    Breed:  Pug
    Color:  brown
    
    Buzo details:
    Buzo is a dog
    Breed:  Bulldog
    Color:  black
    
    Accessing class variable using class name
    dog
    

### Constructors in Python
Constructors are generally used for instantiating an object. The task of constructors is to initialize(assign values) to the data members of the class when an object of the class is created. In Python the __init__() method is called the constructor and is always called when an object is created.

**Syntax of constructor declaration :** 

```Python
def __init__(self):
    # body of the constructor
```

**Types of constructors :**

- **default constructor**: The default constructor is a simple constructor which doesn’t accept any arguments. Its definition has only one argument which is a reference to the instance being constructed.
- **parameterized constructor**: constructor with parameters is known as parameterized constructor. The parameterized constructor takes its first argument as a reference to the instance being constructed known as self and the rest of the arguments are provided by the programmer.


```python
class DefaultConstructor:

    # default constructor
    def __init__(self):
        self.type = "This is default constructor example"

    # a method for printing data members
    def print_type(self):
        print(self.type)


# creating object of the class
obj = DefaultConstructor()

# calling the instance method using the object obj
obj.print_type()

```

    This is default constructor example
    


```python
# parameterized Constructor
class Addition:
    first = 0
    second = 0
    answer = 0

    # parameterized constructor
    def __init__(self, f, s):
        self.first = f
        self.second = s

    def display(self):
        print("First number = " + str(self.first))
        print("Second number = " + str(self.second))
        print("Addition of two numbers = " + str(self.answer))

    def calculate(self):
        self.answer = self.first + self.second

# creating object of the class
# this will invoke parameterized constructor
obj = Addition(1000, 2000)

# perform Addition
obj.calculate()

# display result
obj.display()

```

    First number = 1000
    Second number = 2000
    Addition of two numbers = 3000
    

### Destructors

Destructors are called when an object gets destroyed. In Python, destructors are not needed as much needed in C++ because Python has a garbage collector that handles memory management automatically.
The __del__() method is a known as a destructor method in Python. It is called when all references to the object have been deleted i.e when an object is garbage collected.

**Syntax of destructor declaration** :
```Python
def __del__(self):
  # body of destructor
```


```python
# Python program to illustrate destructor
class Employee:

    # Initializing
    def __init__(self):
        print('Employee created.')

    # Deleting (Calling destructor)
    def __del__(self):
        print('Destructor called, Employee deleted.')

obj = Employee()
del obj



```

    Employee created.
    Destructor called, Employee deleted.
    

### Inheritance in Python

Inheritance is the capability of one class to derive or inherit the properties from another class. The benefits of inheritance are: 
 
- It represents real-world relationships well.
- It provides reusability of a code. We don’t have to write the same code again and again. Also, it allows us to add more features to a class without modifying it.
- It is transitive in nature, which means that if class B inherits from another class A, then all the subclasses of B would automatically inherit from class A.


```python
# A Python program to demonstrate inheritance

# Base or Super class. Note object in bracket.
# (Generally, object is made ancestor of all classes)
# In Python 3.x "class Person" is
# equivalent to "class Person(object)"
class Person:

    # Constructor
    def __init__(self, name):
        self.name = name

    # To get name
    def getName(self):
        return self.name

    # To check if this person is an employee
    def isEmployee(self):
        return False


# Inherited or Subclass (Note Person in bracket)
class Employee(Person):

    # Here we return true
    def isEmployee(self):
        return True

# Driver code
emp = Person("Geek1") # An Object of Person
print(emp.getName(), emp.isEmployee())

emp = Employee("Geek2") # An Object of Employee
print(emp.getName(), emp.isEmployee())


```

    Geek1 False
    Geek2 True
    


```python
# Python code to demonstrate how parent constructors
# are called.

# parent class
class Person( object ):	

        # __init__ is known as the constructor		
        def __init__(self, name, idnumber):
                self.name = name
                self.idnumber = idnumber
        def display(self):
                print(self.name)
                print(self.idnumber)

# child class
class Employee( Person ):		
        def __init__(self, name, idnumber, salary, post):
                self.salary = salary
                self.post = post

                # invoking the __init__ of the parent class
                Person.__init__(self, name, idnumber)


# creation of an object variable or an instance
a = Employee('Rahul', 886012, 200000, "Intern")	

# calling a function of the class Person using its instance
a.display()

```

    Rahul
    886012
    

## Types of inheritance Python

Types of Inheritance depends upon the number of child and parent classes involved. There are four types of inheritance in Python:

- **Single Inheritance** : Single inheritance enables a derived class to inherit properties from a single parent class, thus enabling code reusability and the addition of new features to existing code.

![inheritance11.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632868110571/Lz13ccO4o.png)


```python
# Python program to demonstrate
# single inheritance


# Base class
class Parent:
    def func1(self):
        print("This function is in parent class.")

# Derived class
class Child(Parent):
    def func2(self):
        print("This function is in child class.")

# Driver's code
object = Child()
object.func1()
object.func2()

```

    This function is in parent class.
    This function is in child class.
    

- **Multiple Inheritance** : When a class can be derived from more than one base class this type of inheritance is called multiple inheritance. In multiple inheritance, all the features of the base classes are inherited into the derived class.


![multiple-inheritance1.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632868127596/C7bW2YS_1.png)


```python
# Python program to demonstrate
# multiple inheritance


# Base class1
class Mother:
    mothername = ""
    def mother(self):
        print(self.mothername)

# Base class2
class Father:
    fathername = ""
    def father(self):
        print(self.fathername)

# Derived class
class Son(Mother, Father):
    def parents(self):
        print("Father :", self.fathername)
        print("Mother :", self.mothername)

# Driver's code
s1 = Son()
s1.fathername = "RAM"
s1.mothername = "SITA"
s1.parents()

```

    Father : RAM
    Mother : SITA
    

- **Multilevel Inheritance** :In multilevel inheritance, features of the base class and the derived class are further inherited into the new derived class. This is similar to a relationship representing a child and grandfather.


![Multilevel-inheritance1.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632868138476/0i6UEUFKP.png)


```python
# Python program to demonstrate
# multilevel inheritance

# Base class
class Grandfather:

    def __init__(self, grandfathername):
        self.grandfathername = grandfathername

# Intermediate class
class Father(Grandfather):
    def __init__(self, fathername, grandfathername):
        self.fathername = fathername

        # invoking constructor of Grandfather class
        Grandfather.__init__(self, grandfathername)

# Derived class
class Son(Father):
    def __init__(self,sonname, fathername, grandfathername):
        self.sonname = sonname

        # invoking constructor of Father class
        Father.__init__(self, fathername, grandfathername)

    def print_name(self):
        print('Grandfather name :', self.grandfathername)
        print("Father name :", self.fathername)
        print("Son name :", self.sonname)

# Driver code
s1 = Son('Prince', 'Rampal', 'Lal mani')
print(s1.grandfathername)
s1.print_name()

```

    Lal mani
    Grandfather name : Lal mani
    Father name : Rampal
    Son name : Prince
    

- **Hierarchical Inheritance** : When more than one derived classes are created from a single base this type of inheritance is called hierarchical inheritance. In this program, we have a parent (base) class and two child (derived) classes.

![Hierarchical-inheritance1.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1632868149404/AbQlP-pe3.png)


```python
# Python program to demonstrate
# Hierarchical inheritance


# Base class
class Parent:
    def func1(self):
        print("This function is in parent class.")

# Derived class1
class Child1(Parent):
    def func2(self):
        print("This function is in child 1.")

# Derivied class2
class Child2(Parent):
    def func3(self):
        print("This function is in child 2.")

# Driver's code
object1 = Child1()
object2 = Child2()
object1.func1()
object1.func2()
object2.func1()
object2.func3()

```

    This function is in parent class.
    This function is in child 1.
    This function is in parent class.
    This function is in child 2.
    

- **Hybrid Inheritance** : Inheritance consisting of multiple types of inheritance is called hybrid inheritance.



```python
# Python program to demonstrate
# hybrid inheritance


class School:
    def func1(self):
        print("This function is in school.")

class Student1(School):
    def func2(self):
        print("This function is in student 1. ")

class Student2(School):
    def func3(self):
        print("This function is in student 2.")

class Student3(Student1, School):
    def func4(self):
        print("This function is in student 3.")

# Driver's code
object = Student3()
object.func1()
object.func2()

```

    This function is in school.
    This function is in student 1. 
    

### Encapsulation in Python

Encapsulation is one of the fundamental concepts in object-oriented programming (OOP). It describes the idea of wrapping data and the methods that work on data within one unit. This puts restrictions on accessing variables and methods directly and can prevent the accidental modification of data. To prevent accidental change, an object’s variable can only be changed by an object’s method. Those types of variables are known as private variable. 

Consider a real-life example of encapsulation, in a company, there are different sections like the accounts section, finance section, sales section etc. The finance section handles all the financial transactions and keeps records of all the data related to finance. Similarly, the sales section handles all the sales-related activities and keeps records of all the sales. Now there may arise a situation when for some reason an official from the finance section needs all the data about sales in a particular month. In this case, he is not allowed to directly access the data of the sales section. He will first have to contact some other officer in the sales section and then request him to give the particular data. This is what encapsulation is. 

- **Protected members**: Protected members (in C++ and JAVA) are those members of the class that cannot be accessed outside the class but can be accessed from within the class and its subclasses. To accomplish this in Python, just follow the convention by prefixing the name of the member by a single underscore “_”.


```python
# Python program to
# demonstrate protected members


# Creating a base class
class Base:
    def __init__(self):

        # Protected member
        self._a = 2

# Creating a derived class
class Derived(Base):
    def __init__(self):

        # Calling constructor of
        # Base class
        Base.__init__(self)
        print("Calling protected member of base class: ")
        print(self._a)

obj1 = Derived()
obj2 = Base()

# Calling protected member
# Outside class will result in
# AttributeError
print(obj2.a)

```

    Calling protected member of base class: 
    2
    


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-28-5cc1cbb664b1> in <module>
         26 # Outside class will result in
         27 # AttributeError
    ---> 28 print(obj2.a)
    

    AttributeError: 'Base' object has no attribute 'a'


- **Private members** :Private members are similar to protected members, the difference is that the class members declared private should neither be accessed outside the class nor by any base class. In Python, there is no existence of Private instance variables that cannot be accessed except inside a class. However, to define a private member prefix the member name with double underscore “__”.


```python
# Python program to
# demonstrate private members

# Creating a Base class
class Base:
    def __init__(self):
        self.a = "Python Training"
        self.__c = " Private Python Training"

# Creating a derived class
class Derived(Base):
    def __init__(self):

        # Calling constructor of
        # Base class
        Base.__init__(self)
        print("Calling private member of base class: ")
        print(self.__c)
# Driver code
obj1 = Base()
print(obj1.a)

obj2 = Derived()
# Uncommenting print(obj1.c) will
# raise an AttributeError

# Uncommenting obj2 = Derived() will
# also raise an AtrributeError as
# private member of base class
# is called inside derived class

```

    Python Training
    Calling private member of base class: 
    


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-32-a14b7edcf524> in <module>
         20 obj1 = Base()
         21 print(obj1.a)
    ---> 22 obj2 = Derived()
         23 # Uncommenting print(obj1.c) will
         24 # raise an AttributeError
    

    <ipython-input-32-a14b7edcf524> in __init__(self)
         16         Base.__init__(self)
         17         print("Calling private member of base class: ")
    ---> 18         print(self.__c)
         19 # Driver code
         20 obj1 = Base()
    

    AttributeError: 'Derived' object has no attribute '_Derived__c'


### Polymorphism in Python

The word polymorphism means having many forms. In programming, polymorphism means the same function name (but different signatures) being used for different types.


```python
# Python program to demonstrate in-built poly-
# morphic functions

# len() being used for a string
print(len("Python"))

# len() being used for a list
print(len([10, 20, 30]))

```

    6
    3
    


```python
# A simple Python function to demonstrate
# Polymorphism

def add(x, y, z = 0):
    return x + y+z

# Driver code
print(add(2, 3))
print(add(2, 3, 4))

```

    5
    9
    


```python
from math import pi

class Rectangle:
    def __init__(self, length, breadth):
        self.l = length
        self.b = breadth
    def perimeter(self):
        return 2*(self.l + self.b)
    def area(self):
        return self.l * self.b

class Circle:
    def __init__(self, radius):
        self.r = radius
    def perimeter(self):
        return 2 * pi * self.r
    def area(self):
        return pi * self.r ** 2

# Initialize the classes
rec = Rectangle(5,3)
cr = Circle(4)
print("Perimter of rectangel: ",rec.perimeter())
print("Area of rectangel: ",rec.area())

print("Perimter of Circle: ",cr.perimeter())
print("Area of Circle: ",cr.area())
```

    Perimter of rectangel:  16
    Area of rectangel:  15
    Perimter of Circle:  25.132741228718345
    Area of Circle:  50.26548245743669
    

- **Polymorphism with Inheritance**: In Python, Polymorphism lets us define methods in the child class that have the same name as the methods in the parent class. In inheritance, the child class inherits the methods from the parent class. However, it is possible to modify a method in a child class that it has inherited from the parent class. This is particularly useful in cases where the method inherited from the parent class doesn’t quite fit the child class. In such cases, we re-implement the method in the child class. This process of re-implementing a method in the child class is known as **Method Overriding**. 


```python
class Bird:
    def intro(self):
        print("There are many types of birds.")

    def flight(self):
        print("Most of the birds can fly but some cannot.")

class sparrow(Bird):
    def flight(self):
        print("Sparrows can fly.")

class ostrich(Bird):
    def flight(self):
        print("Ostriches cannot fly.")

obj_bird = Bird()
obj_spr = sparrow()
obj_ost = ostrich()

obj_bird.intro()
obj_bird.flight()

obj_spr.intro()
obj_spr.flight()

obj_ost.intro()
obj_ost.flight()

```

    There are many types of birds.
    Most of the birds can fly but some cannot.
    There are many types of birds.
    Sparrows can fly.
    There are many types of birds.
    Ostriches cannot fly.
    
## Abstract Class

Abstraction means hiding the complexity of the implementation and just exposing the essential features to the user. As an example, you can take any electronics item where you interact with the product using buttons and switches to turn it on and off or increase and decrease the volume or speed. The real complexity, how that functionality is implemented is hidden from us.

```python 
from abc import ABC, abstractmethod

class User(ABC):
    def __init__(self, name, num_of_months):
        self.name = name
        self.num_of_months = num_of_months

    # concrete method
    def display_user(self):
        print('User %s subscribed for %d months' % (self.name, self.num_of_months))

    # abstract method
    @abstractmethod
    def process_fee(self):
        pass

class PlatinumUser(User):
    PLATINUM_PACKAGE = 2200

    def process_fee(self):
        return self.num_of_months * PlatinumUser.PLATINUM_PACKAGE


class GoldUser(User):
    Gold_PACKAGE = 1500

    def process_fee(self):
        return self.num_of_months * GoldUser.Gold_PACKAGE
    

obj = PlatinumUser('Mike Dallas', 8)
obj.display_user()
fee = obj.process_fee()
print('Fee is', fee)

obj = GoldUser('Goldie Hawn', 6)
obj.display_user()
fee = obj.process_fee()
print('Fee is', fee)

obj = PlatinumUser('Ashish Mishra', 10)
obj.display_user()
fee = obj.process_fee()
print('Fee is', fee)
```
    User Mike Dallas subscribed for 8 months
    Fee is 17600
    User Goldie Hawn subscribed for 6 months
    Fee is 9000
    User Ashish Mishra subscribed for 10 months
    Fee is 22000

```python
# Python program demonstrate  
# abstract base class work   
from abc import *   
class Car(ABC):
    @abstractmethod
    def mileage(self):   
        pass  

class Tesla(Car):   
    def mileage(self):   
        print("The mileage is 30kmph")   
class Suzuki(Car):   
    def mileage(self):   
        print("The mileage is 25kmph ")   
class Duster(Car):   
     def mileage(self):   
        print("The mileage is 24kmph ")   

class Renault(Car):   
    def mileage(self):   
            print("The mileage is 27kmph ")   
          
# Driver code   
t= Tesla ()   
t.mileage()   
  
r = Renault()   
r.mileage()   
  
s = Suzuki()   
s.mileage()   
d = Duster()   
d.mileage()  
```
    The mileage is 30kmph
    The mileage is 27kmph 
    The mileage is 25kmph 
   The mileage is 24kmph 

```python
"""
Example: You can't create an object of derived class until,
you implement all its Abstract method
"""
from abc import ABC,abstractmethod

class X(ABC):
    @abstractmethod
    def m1(self):
        pass
    
    @abstractmethod
    def m2(self):
        pass
    
class Y(X):
    def m1(self):
        print("this is an implementation of m1")

y=Y()
```
```
TypeError: Can't instantiate abstract class Y with abstract methods m2
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-25-796b12f9ac4a> in <module>
     14         print("this is an implementation of m1")
     15 
---> 16 y=Y()

TypeError: Can't instantiate abstract class Y with abstract methods m2
```
```python
""" 
Correct way of doing above example
"""

from abc import ABC,abstractmethod

class X(ABC):
    @abstractmethod
    def m1(self):
        pass
    
    @abstractmethod
    def m2(self):
        pass
    
class Y(X):
    def m1(self):
        print("this is an implementation of m1")
        
class Z(Y):
    def m2(self):
        print("this is an implementation of m2")
    
z=Z()
z.m1()
z.m2()
```
```
 this is an implementation of m1
this is an implementation of m2
```
