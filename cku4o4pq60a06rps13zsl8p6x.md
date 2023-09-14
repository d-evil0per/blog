---
title: "File Handling in Python"
seoTitle: "File Handling in Python"
seoDescription: "File Handling, Python Read and Write File (JSON, XML, CSV, xlsx)"
datePublished: Tue Sep 28 2021 22:45:47 GMT+0000 (Coordinated Universal Time)
cuid: cku4o4pq60a06rps13zsl8p6x
slug: file-handling-in-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1632869090374/y_YTWTHxG.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1632869111350/TvXPbRR750.jpeg
tags: python, python-beginner

---

Python too supports file handling and allows users to handle files i.e., to read and write files, along with many other file handling options, to operate on files.


### Working of open() function

We use **open ()** function in Python to open a file in read or write mode. As explained above, open ( ) will return a file object. To return a file object we use open() function along with two arguments, that accepts file name and the mode, whether to read or write. So, the syntax being: open(filename, mode). There are three kinds of mode, that Python provides and how files can be opened:

- “ **r** “, for reading.
- “ **w** “, for writing.
- “ **a** “, for appending.
- “ **r+** “, for both reading and writing

One must keep in mind that the mode argument is not mandatory. If not passed, then Python will assume it to be “ **r** ” by default. Let’s look at this program and try to analyze how the read mode works:


```python
# a file named "geek", will be opened with the reading mode.
file = open('test.txt', 'r')
# This will print every line one by one in the file
for each in file:
    print (each)

```

     this is test file for understanding 
    
    the concept of file handling
    

### Working of read() mode

There is more than one way to read a file in Python. If you need to extract a string that contains all characters in the file then we can use **file.read()**. The full code would work like this:


```python
# Python code to illustrate read() mode
file = open("test.txt", "r")
print (file.read())

```

     this is test file for understanding 
    the concept of file handling
    


```python
# Python code to illustrate read() mode character wise
file = open("test.txt", "r")
print (file.read(5))

```

     this
    

### Creating a file using write() mode

Let’s see how to create a file and how write mode works:
To manipulate the file, write the following in your Python environment:


```python
# Python code to create a file
file = open('geek.txt','w')
file.write("This is the write command")
file.write("It allows us to write in a particular file")
file.close()

```

### Working of append() mode

Let’s see how the append mode works:


```python
# Python code to illustrate append() mode
file = open('geek.txt','a')
file.write("This will add this line")
file.close()

```

### Using write along with with() function

We can also use write function along with with() function:



```python

# Python code to illustrate with() alongwith write()
with open("file.txt", "w") as f: 
    f.write("Hello World!!!") 
```

### split() using file handling

We can also split lines using file handling in Python. This splits the variable when space is encountered. You can also split using any characters as we wish. Here is the code:


```python
# Python code to illustrate split() function
with open("file.txt", "r") as file:
    data = file.readlines()
    for line in data:
        word = line.split()
        print (word)

```

    ['Hello', 'World!!!']
    

### Working With Binary




```python
f1=open("python.jpg", "rb")
f2=open("newpic.jpg", "wb")
bytes=f1.read()
f2.write(bytes)
print("New Image is available with the name: newpic.jpg")
```

    New Image is available with the name: newpic.jpg
    

## Python Read and Write File (JSON, XML, CSV, xlsx) – Sample Code

### JSON Files – Read and Write from Python :

- Write JSON Objects into Python :


```python
# Converting the JSON objects to print in Python
import json
# some JSON:
x =  '{ "city":"Washington", "population":300000, "country":"US"}'
# parse x:
y = json.loads(x)
# the result is a Python dictionary:
print(y["city"])
```

    Washington
    

- Converting Python Objects to JSON :


```python
import json
# Python Dictionary object:
x = {
  "city":"Washington", 
  "population":300000, 
  "country":"US"
}

# convert into JSON:
y = json.dumps(x)

# the result is a JSON string:
print(y)
```

    {"city": "Washington", "population": 300000, "country": "US"}
    

- Read JSON File :


```python
import json
import pandas as pd

with open('file.json') as f:
    data= json.loads(f.read())
print(data)

# We can do the same thing with pandas
data_df = pd.read_json('file.json', orient='records')
print(data_df)

# To Pretty Print
print(json.dumps(data, indent = 4, sort_keys=True))
```

    {'employee': {'name': 'sonoo', 'salary': 56000, 'married': True}}
            employee
    married     True
    name       sonoo
    salary     56000
    {
        "employee": {
            "married": true,
            "name": "sonoo",
            "salary": 56000
        }
    }
    

- Write JSON Data to a File :


```python
import json
import pandas as pd

data_dict = {
  "city":"Washington", 
  "population":300000, 
  "country":"US"
}

with open('file.txt', 'w') as json_file:
    json.dump(data_dict, json_file)
    
# We can do the same thing with pandas
df= pd.DataFrame.from_dict(data_dict, orient='index')
df.to_json('file.json', orient='records')
```

### XML Files – Read and Write from Python :

```xml
<nodedetails>
  <name>SERVER-1</name>
  <description/>
  <numExecutors>SOME_NO_XX</numExecutors>
  <mode>SOME_MODE_XX</mode>
  <launcher class="xxxxx" plugin="xxxxx">
    <hostname>128.0.0.1</hostname>
    <portno>9900</portno>
    <credentialsId>TESTID</credentialsId>
    <maxNumRetries>3</maxNumRetries>
  </launcher>
  <label>somelabel</label>
</nodedetails>
```

- Read from the XML File using ElementTree :


```python
import xml.etree.ElementTree as ET
tree = ET.parse("TEST.xml")
root = tree.getroot()

for item in root.iter('nodedetails'):
    for name in item.iter("name"):
        print (name.text)
    for portno in item.iter("portno"):
        print (portno.text)
```

    SERVER-1
    9900
    

- Read from any XML File using Beautifulsoup :


```python
from bs4 import BeautifulSoup

with open('TEST.xml', 'r') as f: 
    data = f.read()

# Beautifulsoup will parse the data 
All_data = BeautifulSoup(data, "xml")

# Finding all instances of any tag  
tag_data = All_data.find_all('hostname')
print(tag_data)
```

    [<hostname>128.0.0.1</hostname>]
    

- Writing an XML File using ElementTree :


```python
import xml.etree.ElementTree as ET

# Parent (root) tag 
data1 = ET.Element('parents')

# Adding a subtag named `children`  inside our root tag "parents"
data2 = ET.SubElement(data1, 'children')

# Adding subtags under the `children` subtag 
grandChild1 = ET.SubElement(data2, 'E4') 
grandChild2 = ET.SubElement(data2, 'D4')

# Adding attributes to the tags under 
# `items` 
grandChild1.set('card', 'Credit_Card') 
grandChild2.set('card', 'Debit_Card')

# Adding text to grandchildren subtags
grandChild1.text = "Only Credit Cards Accepted"
grandChild2.text = "Only Debit Cards Accepted"

# Convert xml data to byte object to write into filestream 
data_xml = ET.tostring(data1)

# Write to a file with operation mode `wb` (write + binary) 
with open("OUTPUT.xml", "wb") as f: 
    f.write(data_xml)

from bs4 import BeautifulSoup

with open('OUTPUT.xml', 'r') as f: 
    data = f.read()

# Beautifulsoup will parse the data 
All_data = BeautifulSoup(data, "xml")
print(All_data)
```

    <?xml version="1.0" encoding="utf-8"?>
    <parents><children><E4 card="Credit_Card">Only Credit Cards Accepted</E4><D4 card="Debit_Card">Only Debit Cards Accepted</D4></children></parents>
    

- Writing to an XML using Beautifulsoup :


```python
#Open file
soup = BeautifulSoup(open('TEST.xml'),'xml')

modified_xml_content = '''<note>
<to>Tove</to>
<from>Jani</from>
<heading>Reminder</heading>
<body>Don't forget me this weekend!</body>
</note>'''

#Write to a file
f = open('OUTPUT.xml', "w")
f.write(str(modified_xml_content))
f.close()
```

### CSV Files – Read and Write from Python :

- Read from CSV File using Native Python Lib :


```python
import csv
rows=[]
with open('sample4.csv') as inputfile:
    csvreader = csv.reader(inputfile, delimiter=',')
    # Extracting each data row one by one 
    for row in csvreader: 
        rows.append(row)
        
# Printing out the first 5 rows 
for row in rows[:5]: 
    print(row)
```

    ['Game Number', ' "Game Length"']
    ['1', ' 30']
    ['2', ' 29']
    ['3', ' 31']
    ['4', ' 16']
    

- Read from CSV File using Pandas Lib :


```python
import pandas as pd
data = pd.read_csv('sample4.csv')
# Display first 10 Lines of data
data.head(10)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Game Number</th>
      <th>"Game Length"</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1</td>
      <td>30</td>
    </tr>
    <tr>
      <td>1</td>
      <td>2</td>
      <td>29</td>
    </tr>
    <tr>
      <td>2</td>
      <td>3</td>
      <td>31</td>
    </tr>
    <tr>
      <td>3</td>
      <td>4</td>
      <td>16</td>
    </tr>
    <tr>
      <td>4</td>
      <td>5</td>
      <td>24</td>
    </tr>
    <tr>
      <td>5</td>
      <td>6</td>
      <td>29</td>
    </tr>
    <tr>
      <td>6</td>
      <td>7</td>
      <td>28</td>
    </tr>
    <tr>
      <td>7</td>
      <td>8</td>
      <td>117</td>
    </tr>
    <tr>
      <td>8</td>
      <td>9</td>
      <td>42</td>
    </tr>
    <tr>
      <td>9</td>
      <td>10</td>
      <td>23</td>
    </tr>
  </tbody>
</table>
</div>



- Write to a CSV File using Native Python lib :


```python
import csv

data = [ ['Emily', '12', '18', '112'], 
         ['Katie', '8', '24', '96'], 
         ['John', '16', '9', '101'], 
         ['Mike', '3', '14', '82']]

writer = csv.writer(open("OUTPUTFILE.csv", 'w'))
for row in data:
    print(row)
    writer.writerow(row)
    
```

    ['Emily', '12', '18', '112']
    ['Katie', '8', '24', '96']
    ['John', '16', '9', '101']
    ['Mike', '3', '14', '82']
    

- Write to a CSV File using pandas :


```python
import pandas as pd

data_dict = {
  "city":"Washington", 
  "population":300000, 
  "country":"US"
}

df= pd.DataFrame.from_dict(data_dict, orient='index')
df.to_csv('OUTPUTFILE.csv')
```

## xlsx Files – Read and Write from Python :

Write to a xlsx File using pandas :


```python
import pandas as pd

data_dict = {
  "city":"Washington", 
  "population":300000, 
  "country":"US"
}

df= pd.DataFrame.from_dict(data_dict, orient='index')
df.to_excel('OUTPUTFILE.xlsx')
```

- Read from xlsx File using Pandas Lib :


```python
import pandas as pd

df=pd.read_excel('OUTPUTFILE.xlsx')
print(df)
```

       Unnamed: 0           0
    0        city  Washington
    1  population      300000
    2     country          US
    

