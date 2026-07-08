# <center>Functions</center>

<hr>

## What is a Function?
A function is a block of organized, reusable code that does one specific thing. You can think of it like a mini program inside your bigger program.

### Here’s why functions are awesome:
- **Modularity** – Instead of writing the same code over and over, you can put it in a function and just call that function whenever needed.
- **Reusability** – Once you write a function, you can use it as many times as you want in your program, making it easier to manage!

You’ve already seen functions like `print()` and `str()`, which are built-in functions. But guess what? You can create your own functions too!

Functions let you **"encapsulate"** a task, meaning you can group many instructions together and then call them with a single line of code.

### Syntax for Defining a Simple Function

In Python, we define a function using a specific syntax. Here’s what it looks like:

```python
def function_name():
    # indented lines of code
    # more lines of code
```

**Understanding the `def` Keyword and Function Syntax**

1. **`def` Keyword:**
   - This keyword tells Python that we are about to define a new function. It stands for "define."
2. **Function Name:**
   - `function_name` is where you give your function a name. This should be descriptive so that anyone reading your code knows what the function does. For example, if our function prints a pyramid, we could name it `print_pyramid`.
3. **Parentheses `()`:**
   - The parentheses are used to define any inputs, called arguments, that the function might need. In this case, we leave them empty because our function doesn’t require any inputs right now.
4. **Colon `:`:**
   - After the parentheses, we put a colon. This signals that the following indented lines of code are part of the function.
5. **Indented Lines:**
   - The lines of code inside the function must be indented. This tells Python which lines belong to this function. Indentation is crucial in Python because it defines the block of code that will execute when the function is called.

### Function Naming Rules

1. **Start with a Letter or Underscore:**
   - A function name must begin with a letter (a-z, A-Z) or an underscore (_).
2. **Allowed Characters:**
   - The name can contain letters (both lower and uppercase) and numbers.
3. **Lowercase with Underscores:**
   - Function names should be written in lowercase, with words separated by underscores as necessary to improve readability. For example: `print_pyramid`.
4. **Variable Names:**
   - Variable names follow the same conventions as function names.

### Example
Let’s see a simple example of a function called `print_pyramid`:

<iframe src="https://trinket.io/embed/python3/73db1988a65b" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

**What Happens When You Run This?**
- If you run the code above as it is, there will be no visible output because we have only defined the function. The function will do nothing until we call it.

### Calling the Function

To see the output, we need to call the function like this:

```python 
print_pyramid()
```

<iframe src="https://trinket.io/embed/python3/ad07e5f6ad6a" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>