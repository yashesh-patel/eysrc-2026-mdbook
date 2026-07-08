<h1 style="text-align: center;">if-elif-else Practice in Python</h1>

<hr>

## Practice Question

let's start easy with a **Square Checker**.
Take the length and breadth from the user and print out if it's a square or a rectangle.

```python
length = int(input("Enter length: "))
breadth = int(input("Enter breadth: "))
# check and print if it's a square or a rectangle

```

Next let's use the greater than condition and build a **Discount Calculator**
A shop will give discount of 10% if the cost of purchased quantity is more than 1000 Rs.
Ask user for quantity
Suppose, one unit will cost 100 Rs.
Print *total cost before and after discount* and *discount applied* for user.

```python
cost_per_unit = 100
n = int(input("Enter quantity to be purchsed: "))
total_cost = 100 * n
discount = 0
# check if total_cost is greater than 1000 and calculate discount



print("Total Cost: " + str(total_cost))
print("Discount Applied: " + str(discount))
print("Amount to be paid: " + str(total_cost - discount))
```

Time for Logical Operators, let's introduce more conditions! Write a program to find the **Greatest of Three Numbers**.

```python
a = int(input("Enter value of a"))
b = int(input("Enter value of b (not equal to a)"))
c = int(input("Enter value of c (not equal to a or b)"))
if a > b and a > c:
        print("a is the greatest of them all!")
elif b > a and b > c:
        print("b is the greatest of them all.")
else:
    	print("c is the greatest of them all.")
```

Make a **Pythogorean Triplet Checker**.

```python
a = int(input("Enter value of side 1 "))
b = int(input("Enter value of side 2 "))
c = int(input("Enter value of hypotenue "))

if  a**2 + b**2 == c**2:
    print("Pythagorian Triplet: " + str(a**2) + " + " + str(b**2) + " equals " + str (c**2))
else:
    print("Not Pythagorian Triplet: " + str(a**2) + " + " + str(b**2) + " not equal to " + str (c**2))

```

**Pythogorian Triplet Checker V2.0**: Now combine the above two programs to write a program that can check if three number entered in <u>*any order*</u> is a pythagorean triplet.

```python
a = int(input("Enter value of side 1 "))
b = int(input("Enter value of side 2 "))
c = int(input("Enter value of side 3 "))
"""
a, b, c are not in any order so first we need to find the hypotenuse by finding the largest of the three then check if they are a pythagorean triplet
"""

```

### HOT (Higher-Order Thinking) Question!

**Greatest of Three Numbers V2.0**: Write a program to find the greatest of three numbers <u>*without using logical operators (and/or/not)*</u>

```python
a = int(input("Enter value of a"))
b = int(input("Enter value of b"))
c = int(input("Enter value of c"))
if a > b:
    if c > a:
        print("c is the greatest of them all!")
    else:
        print("a is the greatest of them all.")
else:
    if c > b:
        print("c is the greatest of them all!")
    else:
    	print("b is the greatest of them all.")
```



