# Reading and Writing Files in Python

## What Is a File?

At its core, a file is a contiguous set of bytes used to store data. This data is organized in a specific format and can be anything as simple as a text file or as complicated as a program executable. In the end, these byte files are then translated into binary 1 and 0 for easier processing by the computer.

1. Files on most modern file systems are composed of three main parts:

2. Header: metadata about the contents of the file (file name, size, type, and so on)

3. Data: contents of the file as written by the creator or editor
   End of file (EOF): special character that indicates the end of the file

## File Paths

When you access a file on an operating system, a file path is required. The file path is a string that represents the location of a file. It’s broken up into three major parts:

1. Folder Path: the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)

2. File Name: the actual name of the file

3. Extension: the end of the file path pre-pended with a period (.) used to indicate the file type



## Line Endings

One problem often encountered when working with file data is the representation of a new line or line ending. The line ending has its roots from back in the Morse Code era, when a specific pro-sign was used to communicate the end of a transmission or the end of a line.

Later, this was standardized for teleprinters by both the International Organization for Standardization (ISO) and the American Standards Association (ASA). ASA standard states that line endings should use the sequence of the Carriage Return (CR or \r) and the Line Feed (LF or \n) characters (CR+LF or \r\n). The ISO standard however allowed for either the CR+LF characters or just the LF character.


## Character Encodings

Another common problem that you may face is the encoding of the byte data. An encoding is a translation from byte data to human readable characters. This is typically done by assigning a numerical value to represent a character. The two most common encodings are the ASCII and UNICODE Formats. ASCII can only store 128 characters, while Unicode can contain up to 1,114,112 characters.

ASCII is actually a subset of Unicode (UTF-8), meaning that ASCII and Unicode share the same numerical to character values. It’s important to note that parsing a file with the incorrect character encoding can lead to failures or misrepresentation of the character. For example, if a file was created using the UTF-8 encoding, and you try to parse it using the ASCII encoding, if there is a character that is outside of those 128 values, then an error will be thrown.

``` file = open('dog_breeds.txt') ```

When you’re manipulating a file, there are two ways that you can use to ensure that a file is closed properly, even when encountering an error. The first way to close a file is to use the try-finally block:

```
reader = open('dog_breeds.txt')
try:
    # Further file processing goes here
finally:
    reader.close()
```

The with statement automatically takes care of closing the file once it leaves the with block, even in cases of error. I highly recommend that you use the with statement as much as possible, as it allows for cleaner code and makes handling any unexpected errors easier for you.

```
with open('dog_breeds.txt', 'r') as reader:
    # Further file processing goes here
```

## Text File Types

A text file is the most common file that you’ll encounter. Here are some examples of how these files are opened:

```
open('abc.txt')

open('abc.txt', 'r')

open('abc.txt', 'w')
```

With these types of files, open() will return a TextIOWrapper file object:

```
>>> file = open('dog_breeds.txt')
>>> type(file)
<class '_io.TextIOWrapper'>
```

## Buffered Binary File Types

A buffered binary file type is used for reading and writing binary files. Here are some examples of how these files are opened:

```
open('abc.txt', 'rb')

open('abc.txt', 'wb')
```

With these types of files, open() will return either a BufferedReader or BufferedWriter file object:

```
>>> file = open('dog_breeds.txt', 'rb')
>>> type(file)
<class '_io.BufferedReader'>
>>> file = open('dog_breeds.txt', 'wb')
>>> type(file)
<class '_io.BufferedWriter'>
```



# Python Exceptions: An Introduction


A Python program terminates as soon as it encounters an error. In Python, an error can be a syntax error or an exception. In this article, you will see what an exception is and how it differs from a syntax error. After that, you will learn about raising exceptions and making assertions. Then, you’ll finish with a demonstration of the try and except block.

![image1](https://files.realpython.com/media/intro.8915db1758d8.png)

## Exceptions versus Syntax Errors

Syntax errors occur when the parser detects an incorrect statement. Observe the following example:

```
>>> print( 0 / 0 ))
  File "<stdin>", line 1
    print( 0 / 0 ))
                  ^
SyntaxError: invalid syntax
```

The arrow indicates where the parser ran into the syntax error. In this example, there was one bracket too many. Remove it and run your code again:

```
>>> print( 0 / 0)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: integer division or modulo by zero
```

This time, you ran into an exception error. This type of error occurs whenever syntactically correct Python code results in an error. The last line of the message indicated what type of exception error you ran into.

Instead of showing the message exception error, Python details what type of exception error was encountered. In this case, it was a ZeroDivisionError. Python comes with various built-in exceptions as well as the possibility to create self-defined exceptions.



## Raising an Exception

We can use raise to throw an exception if a condition occurs. The statement can be complemented with a custom exception.

![image2](https://files.realpython.com/media/raise.3931e8819e08.png)

If you want to throw an error when a certain condition occurs using raise, you could go about it like this:

```
x = 10
if x > 5:
    raise Exception('x should not exceed 5. The value of x was: {}'.format(x))
```

When you run this code, the output will be the following:

```
Traceback (most recent call last):
  File "<input>", line 4, in <module>
Exception: x should not exceed 5. The value of x was: 10
```

