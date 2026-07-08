<h1 style="text-align: center;">Logical Operators</h1>

## Logical Operators

Logical operators are used to combine conditional statements.

Let's take the same example:

```python
box1 = 10  
box2 = 20
```

1. **Logical OR (`or`)**: If one of the operands or expressions is `True`, it will return `True`.  
   Consider the expression **box1 < box2 or box1 == box2** — it would return `True` as one of the expressions, `box1 < box2`, is `True`.

2. **Logical AND (`and`)**: If both the left and right operands or expressions are `True`, it will return `True`. Otherwise, it will return `False`.  
   Consider the expression **box1 == 10 and box2 > box1** — it would return `True` as both conditions are `True`.

3. **Logical NOT (`not`)**: The `not` operator is used to reverse the result of a condition.  
   If the current state is `True`, `not` will make it `False`, and vice versa.  
   Consider the expression **not (box1 == 10 and box2 > box1)** — it would return `False` as both expressions are `True`, and the reverse of `True` is `False`.


Logical operators can be better understood with the help of **truth tables**. A truth table is a simple way to visualize how a logical operator behaves with different inputs. Each logical operator produces an output based on whether the inputs are **True** or **False**.


### Combined Truth Table for Logical Operators

| X | Y | X and Y | X or Y | not(X) | not(Y) |
|---|---|----------|---------|--------|--------|
| T | T |    T     |    T    |   F    |   F    |
| T | F |    F     |    T    |   F    |   T    |
| F | T |    F     |    T    |   T    |   F    |
| F | F |    F     |    F    |   T    |   T    |


<br>

<iframe src="https://trinket.io/embed/python/1942ce3c70ef" width="100%" height="360" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


## Identity Operators

Identity operators are used to check whether two variables refer to the **same object in memory**. Python provides two identity operators: `is` and `is not`.

1. **`is`**: This operator returns `True` if both variables point to the **same object** in memory.

   **Example**: The expression `box1 is box2` returns `False` if `box1` and `box2` do not refer to the same object.

2. **`is not`**: This operator returns `True` if the two variables **do not refer** to the same object in memory.

   **Example**: The expression `box1 is not box2` returns `True` if `box1` and `box2` are different objects.

   
<iframe src="https://trinket.io/embed/python/3e64a88fc9f4" width="100%" height="360" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>