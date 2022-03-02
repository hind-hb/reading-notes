# FileIO & Exceptions


** What Is File**
*a file is a contiguous set of bytes used to store data. This data is organized in a specific format and can be anything as simple as a text file or as complicated as a program executable*

**Files Parts**
* `Header` : Include The MetaDdata Which Content the info about File
* `Data` : Contents of the file
* `End Of The File` :  special character that indicates the end of the file

**File Paths**
*The File Path is a String that present the location of the file in The OS*

**Path Parts**
* Folder Path 
* File Name
* File Extension

**Opening and Closing a File in Python**
*To Open a file in python we use the `open()` method that take a one parameter which is a file path*

```
file_path = 'README.md'
file = open(file_path)
```
`We always Need To close the file after finish working with`

*we have to ways to close the file*

**The First One **
`using try-finally`

```
file_path = 'README.md'
reader = open(file_path)
try:
    # Further file processing goes here
finally:
    reader.close()

```
**The second way**
`using with statment`

```
file_path = 'README.md'
with open(file_path) as reader:
    # Further file processing goes here

```

**The with statement automatically takes care of closing the file once it leaves the with block**

## three different categories of file objects:
- Text files
- Buffered binary files
- Raw binary files

**Reading and Writing Opened Files**
- Reading we can read from the file using three method 
  * read()
  * readline()
  * readlines()
  
  **For Example**
  
  ```
  filepath = 'aghyad.txt'

  
  with open(filepath, 'r') as reader:
    print(reader.read())

  ```
**Iterating Over Each Line in the File**

```
with open(filepath, 'r') as reader:

    line = reader.readline()
    while line != '':

        print(line, end='')
        line = reader.readline()
```

## Python Exceptions

**Exceptions versus Syntax Errors**
Syntax errors occur when the parser detects an incorrect statement.Where exception error This type of error occurs whenever syntactically correct Python code results in an error.

```
print( 0 / 0 ))
  File "<stdin>", line 1
    print( 0 / 0 ))
                  ^
SyntaxError: invalid syntax
```

**The try and except Block: Handling Exceptions**
The try and except block in Python is used to catch and handle exceptions.

```
try:
    linux_interaction()
except:
    print('Linux function was not executed')
```
**For Example :**
```
try:
    linux_interaction()
except AssertionError as error:
    print(error)
else:
    print('Executing the else clause.')
```  
    
**Cleaning Up After Using finally**
Imagine that you always had to implement some sort of action to clean up after executing your code. Python enables you to do so using the finally clause.
