---
title: "String Objects in Python"
seoTitle: "String Objects in Python"
seoDescription: "String Slicing, Escape Sequencing in Python, Formatting of Strings, Built-in Functions"
datePublished: Tue Sep 28 2021 22:41:24 GMT+0000 (Coordinated Universal Time)
cuid: cku4nz34409wzp9s1g2jggmzj
slug: string-objects-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1632868717452/C2cQTQVvS.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1632868838225/dDlGeuAdi.png
tags: python, python-beginner

---

Strings are arrays of bytes representing Unicode characters. However, Python does not have a character data type, a single character is simply a string with a length of 1. Square brackets can be used to access elements of the string.


```python
# Python Program for
# Creation of String

# Creating a String
# with single Quotes
String1 = 'Welcome to the Geeks World'
print("String with the use of Single Quotes: ")
print(String1)

# Creating a String
# with double Quotes
String1 = "I'm a Geek"
print("\nString with the use of Double Quotes: ")
print(String1)

# Creating a String
# with triple Quotes
String1 = '''I'm a Geek and I live in a world of "Geeks"'''
print("\nString with the use of Triple Quotes: ")
print(String1)

# Creating String with triple
# Quotes allows multiple lines
String1 = '''Geeks
            For
            Life'''
print("\nCreating a multiline String: ")
print(String1)

```

    String with the use of Single Quotes: 
    Welcome to the Geeks World
    
    String with the use of Double Quotes: 
    I'm a Geek
    
    String with the use of Triple Quotes: 
    I'm a Geek and I live in a world of "Geeks"
    
    Creating a multiline String: 
    Geeks
                For
                Life
    

### String Slicing
To access a range of characters in the String, method of slicing is used. Slicing in a String is done by using a Slicing operator (colon). 


```python
# Python Program to
# demonstrate String slicing

# Creating a String
String1 = "GeeksForGeeks"
print("Initial String: ")
print(String1)

# Printing 3rd to 12th character
print("\nSlicing characters from 3-12: ")
print(String1[3:12])

# Printing characters between
# 3rd and 2nd last character
print("\nSlicing characters between " +
    "3rd and 2nd last character: ")
print(String1[3:-2])

```

    Initial String: 
    GeeksForGeeks
    
    Slicing characters from 3-12: 
    ksForGeek
    
    Slicing characters between 3rd and 2nd last character: 
    ksForGee
    

### Escape Sequencing in Python
While printing Strings with single and double quotes in it causes SyntaxError because String already contains Single and Double Quotes and hence cannot be printed with the use of either of these. Hence, to print such a String either Triple Quotes are used or Escape sequences are used to print such Strings. 
Escape sequences start with a backslash and can be interpreted differently. If single quotes are used to represent a string, then all the single quotes present in the string must be escaped and the same is done for Double Quotes. 


```python
# Python Program for
# Escape Sequencing
# of String

# Initial String
String1 = '''I'm a "Geek"'''
print("Initial String with use of Triple Quotes: ")
print(String1)

# Escaping Single Quote
String1 = 'I\'m a "Geek"'
print("\nEscaping Single Quote: ")
print(String1)

# Escaping Double Quotes
String1 = "I'm a \"Geek\""
print("\nEscaping Double Quotes: ")
print(String1)

# Printing Paths with the
# use of Escape Sequences
String1 = "C:\\Python\\Geeks\\"
print("\nEscaping Backslashes: ")
print(String1)

```

    Initial String with use of Triple Quotes: 
    I'm a "Geek"
    
    Escaping Single Quote: 
    I'm a "Geek"
    
    Escaping Double Quotes: 
    I'm a "Geek"
    
    Escaping Backslashes: 
    C:\Python\Geeks\
    


```python
# Printing Geeks in HEX
String1 = "This is \x47\x65\x65\x6b\x73 in \x48\x45\x58"
print("\nPrinting in HEX with the use of Escape Sequences: ")
print(String1)

# Using raw String to
# ignore Escape Sequences
String1 = r"This is \x47\x65\x65\x6b\x73 in \x48\x45\x58"
print("\nPrinting Raw String in HEX Format: ")
print(String1)

```

    
    Printing in HEX with the use of Escape Sequences: 
    This is Geeks in HEX
    
    Printing Raw String in HEX Format: 
    This is \x47\x65\x65\x6b\x73 in \x48\x45\x58
    

### Formatting of Strings
Strings in Python can be formatted with the use of the format() method which is a very versatile and powerful tool for formatting Strings. Format method in String contains curly braces {} as placeholders which can hold arguments according to position or keyword to specify the order.


```python
# Python Program for
# Formatting of Strings

# Default order
String1 = "{} {} {}".format('Geeks', 'For', 'Life')
print("Print String in default order: ")
print(String1)

# Positional Formatting
String1 = "{1} {0} {2}".format('Geeks', 'For', 'Life')
print("\nPrint String in Positional order: ")
print(String1)

# Keyword Formatting
String1 = "{l} {f} {g}".format(g = 'Geeks', f = 'For', l = 'Life')
print("\nPrint String in order of Keywords: ")
print(String1)

```

    Print String in default order: 
    Geeks For Life
    
    Print String in Positional order: 
    For Geeks Life
    
    Print String in order of Keywords: 
    Life For Geeks
    


```python
# Formatting of Integers
String1 = "{0:b}".format(16)
print("\nBinary representation of 16 is ")
print(String1)

# Formatting of Floats
String1 = "{0:e}".format(165.6458)
print("\nExponent representation of 165.6458 is ")
print(String1)

# Rounding off Integers
String1 = "{0:.2f}".format(1/6)
print("\none-sixth is : ")
print(String1)

```

    
    The binary representation of 16 is 
    10000
    
    Exponent representation of 165.6458 is 
    1.656458e+02
    
    one-sixth is : 
    0.17
    


```python
# String alignment
String1 = "|{:<10}|{:^10}|{:>10}|".format('Geeks','for','Geeks')
print("\nLeft, center and right alignment with Formatting: ")
print(String1)

# To demonstrate aligning of spaces
String1 = "\n{0:^16} was founded in {1:<4}!".format("GeeksforGeeks", 2009)
print(String1)

```

    
    Left, center and right alignment with Formatting: 
    |Geeks     |   for    |     Geeks|
    
     GeeksforGeeks   was founded in 2009!
    

### Built-in Functions

1. **capitalize()**
Capitalizes first letter of string

2. **center(width, fillchar)**
Returns a space-padded string with the original string centered to a total of width columns.

3. **count(str, beg= 0,end=len(string))**
Counts how many times str occurs in string or in a substring of string if starting index beg and ending index end are given.

4. **decode(encoding='UTF-8',errors='strict')**
Decodes the string using the codec registered for encoding. encoding defaults to the default string encoding.

5. **encode(encoding='UTF-8',errors='strict')**
Returns encoded string version of string; on error, default is to raise a ValueError unless errors is given with 'ignore' or 'replace'.

6. **endswith(suffix, beg=0, end=len(string))**
Determines if a string or a substring of string (if starting index beg and ending index end are given) ends with a suffix; returns true if so and false otherwise.

7. **expandtabs(tabsize=8)**
Expands tabs in the string to multiple spaces; defaults to 8 spaces per tab if tab size not provided.

8. **find(str, beg=0 end=len(string))**
Determine if str occurs in string or in a substring of string if starting index beg and ending index end are given returns index if found and -1 otherwise.

9. **index(str, beg=0, end=len(string))**
Same as find(), but raises an exception if str not found.

10. **isalnum()**
Returns true if the string has at least 1 character and all characters are alphanumeric and false otherwise.

11. **isalpha()**
Returns true if the string has at least 1 character and all characters are alphabetic and false otherwise.

12. **isdigit()**
Returns true if the string contains only digits and false otherwise.

13. **islower()**
Returns true if the string has at least 1 cased character and all cased characters are in lowercase and false otherwise.

14. **isnumeric()**
Returns true if a Unicode string contains only numeric characters and false otherwise.

15. **isspace()**
Returns true if the string contains only whitespace characters and false otherwise.

16. **istitle()**
Returns true if the string is properly "title cased" and false otherwise.

17. **isupper()**
Returns true if the string has at least one cased character and all cased characters are in uppercase and false otherwise.

18. **join(seq)**
Merges (concatenates) the string representations of elements in sequence seq into a string, with separator string.

19. **len(string)**
Returns the length of the string

20. **ljust(width[, fillchar])**
Returns a space-padded string with the original string left-justified to a total of width columns.

21. **lower()**
Converts all uppercase letters in a string to lowercase.

22. **lstrip()**
Removes all leading whitespace in string.

23. **maketrans()**
Returns a translation table to be used in the translate function.

24. **max(str)**
Returns the max alphabetical character from the string str.

25. **min(str)**
Returns the min alphabetical character from the string str.

26. **replace(old, new [, max])**
Replaces all occurrences of old in a string with new or at most max occurrences if max gave.

27. **rfind(str, beg=0,end=len(string))**
Same as find(), but search backwards in string.

28. **rindex( str, beg=0, end=len(string))**
Same as index(), but search backwards in string.

29. **rjust(width,[, fillchar])**
Returns a space-padded string with the original string right-justified to a total of width columns.

30. **rstrip()**
Removes all trailing whitespace of string.

31. **split(str="", num=string.count(str))**
Splits string according to delimiter str (space if not provided) and returns a list of substrings; split into at most num substrings if given.

32. **splitlines( num=string.count('\n'))**
Splits string at all (or num) NEWLINEs and returns a list of each line with NEWLINEs removed.p>

33. **startswith(str, beg=0,end=len(string))**
Determines if a string or a substring of string (if starting index beg and ending index end are given) starts with substring str; returns true if so and false otherwise.

34. **strip([chars])**
Performs both lstrip() and rstrip() on string.

35. **swapcase()**
Inverts case for all letters in string.

36. **title()**
Returns "title cased" version of the string, that is, all words begin with uppercase and the rest are lowercase.

37. **translate(table, deletechars="")**
Translates string according to translation table str(256 chars), removing those in the del string.

38. **upper()**
Converts lowercase letters in a string to uppercase.

39. **zfill (width)**
Returns original string left padded with zeros to a total of width characters; intended for numbers, zfill() retains any sign given (less one zero).

40. **isdecimal()**
Returns true if a Unicode string contains only decimal characters and false otherwise.
