<h1 style="text-align: center;">Integer</h1>

<hr>

## int

Like in math, integers in computer programming are whole numbers without a fractional part. They can be positive, negative, or zero, and have unlimited precision. Examples include 0, 100, and -10 (…,-1, 0, 1,…). An integer is often referred to as an `int`.

As with other programming languages, you should not use commas in numbers with four or more digits. For example, instead of writing 1,000 in your program, write `1000`.

### Syntax :

<iframe src="https://trinket.io/embed/python3/37c7fc4b71" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

<br>

## type()
You can get the data type of any object by using the `type()` function:

### Syntax :

```python
type(<variable_name>)
```
### For Example :

<iframe src="https://trinket.io/embed/python3/fe0275fe4e" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

<br>

All integer literals or variables are objects of the `int` class.

If we want the Python program to get two integer values as input from the user then how will you do that?

Do you remember in `Variables` chapter we talked about `input()` function?

Let's take two integers as input and perform addition of these two numbers.

<iframe src="https://trinket.io/embed/python3/d76742f9ba" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
<br>

Did you get the output in the form of `xy` instead of the sum of `x` and `y`? This happens because the input() function reads the input and always converts it into a string. That’s why the inputs `x` and `y` are treated as `strings`, resulting in the concatenation of these two inputs instead of their sum.

### For example :

In the above program, if we give the first number as 10 and the second number as 20, the answer will not be 30.

Instead, it will show the concatenation of 10 and 20 (since the inputs are taken as strings).

So, the output will be `1020`.

To get the correct result, we need to `typecast` the input based on our need.

## Type Casting

It is the method to convert the variable of one data type to another in order to the operation required to be performed by users.

Using `int()` function we can convert the string input to integer.

### For example:


<iframe src="https://trinket.io/embed/python3/216f39a33b" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

> [!NOTE]
> Note that integers must be without a fractional part (decimal point). If it includes a fractional then it becomes a **float**.

