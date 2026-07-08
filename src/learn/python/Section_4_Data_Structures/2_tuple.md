<h1 style="text-align: center;">Tuples</h1>

<hr>

## Tuple

You may not always want your data to be changed. Using a tuple instead of a list helps prevent unwanted alterations, especially when the values are meant to remain constant throughout the program.

A **tuple** is a container for a set of comma-separated values (items or elements) enclosed in parentheses—for example, a coordinate like `(x, y)`. Tuples are similar to lists, but unlike lists, **they are immutable**, meaning you **cannot change, add, or remove** elements after the tuple is created.

#### Syntax

```python
variable_name = (item1, item2, .....itemN)
```

#### For example

```python
box = ('Maths', 'Science', 'English', 'History', 'Physics')
```

<iframe src="https://trinket.io/embed/python3/61c6dbaf38" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Accessing Elements of Tuple

Similar to lists, each element in a **tuple** can be accessed using an **index inside square brackets** `[ ]`, or by **slicing** using a range of indices to retrieve multiple values.

Just like lists, indexing in tuples starts at **0** and goes up to **(number of elements - 1)**.

<iframe src="https://trinket.io/embed/python3/c411e73790" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Updating Tuple

Tuples, as previously stated, are **immutable**, meaning their values **cannot be modified directly**. However, we can **create new tuples by combining parts of existing tuples**.

This way, instead of modifying a tuple, we generate a new one through **concatenation**.

<iframe src="https://trinket.io/embed/python3/31bb8d6e80" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Delete Elements from Tuple

Individual tuple elements **cannot be removed**, since tuples are immutable. However, you can always create a **new tuple** that excludes the unwanted elements.

#### Syntax

```python
del tuple_name;
```

Simply `use` the del statement to remove an entire tuple.

#### For example

<br>

<iframe src="https://trinket.io/embed/python3/08f69c2bab" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

As a result, you'll get the above outcome — an error is triggered because after using `del tup`, the tuple no longer exists.

## Convert List to Tuple

In Python, you can convert lists and tuples to each other using the `list()` and `tuple()` functions.

To convert a **tuple** to a **list**, pass the tuple to the `list()` function.


#### Syntax

```python
list(tuple_name)
```

#### For example

<br>

<iframe src="https://trinket.io/embed/python3/92198a0cc8" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

To convert a **list** to a **tuple**, pass the list to the `tuple() `function.

#### Syntax

```python
tuple(list_name)
```

#### For example

<br>

<iframe src="https://trinket.io/embed/python3/7ac38f36b1" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Basic Tuple Operations

- `len()` : Returns the total number of items in the tuple.
- `min()` : Returns the item with the lowest value in the tuple.
- `max()` : Returns the item with the highest value in the tuple.

<iframe src="https://trinket.io/embed/python3/268579f3e0" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>