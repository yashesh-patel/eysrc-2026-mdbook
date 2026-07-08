<h1 style="text-align: center;"> Syntax and Comments</h1>
<hr>

In this section we will learn about Python syntax, including what it is and how it differs from other programming languages. 

## Python Syntax

The Python syntax defines all the set of rules that are used to create sentences in Python programming. The Python syntax is a set of rules that are used in Python programming to construct sentences.

For instance, in order to learn English, we must first master grammar. Similarly, in order to learn Python, you must first learn and understand the Python syntax. 


## Python Indentation

Python does not use braces ({}) similar to other languages like C, C++ to indicate code blocks for class and function definitions or flow control.

Python uses indentation (4 spaces/tab) to define code block.

**For example :**<br>

```python
a = 3
if a>5:
    print("Hi!")
else:
    print("Bye!")
```

In the above example the whitespaces before the `print` statements indicates indentation.
Well! We will learn about indentation more in control flow and functions. 


## Python Comment Statements

In Python, the symbol `#` indicates the start of the comment line. The Python interpreter ignores all characters after the # and up to the end of the physical line as part of the comment. 

**For example :**<br>

```python
#This is a comment
print("Hello World!")
```

Python does not have any syntax for multi-line comments, such as the `/* ... */` syntax used in C and C++. For multi-line comments, each line should have the # symbol at the start. 

```python
#Line1
#Line2
#Line3
```

But multi-line strings are often used as a replacement for multi-line comments.

Three double-quotes are used to delimit a docstring.

```python
'''
this is a 
multiline
comment
'''
```