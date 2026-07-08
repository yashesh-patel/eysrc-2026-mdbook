<h1 style="text-align: center;">Infinite Loop and Break & Continue</h1>

<hr>

Before we get into the Break and Continue statement lets pose a problem to motivate the use of break and continue statements.

## Infinite Loops

Question: Can you guess what would would happen if we wrote the following code?

```python
while True:
	print("hello")
```

Well, it must be easy to see that the condition "is True True?" is always True. That is, the condition will never fail and the loop will run infinitely untill the program crashes or something within the body of the loop stops the loop.

**Infinite Loops are awesome!** We use them all the time in many different applications of game development, robotics etc. But then how does a program terminate if have infinite loops?

Let's build a very very simple game, the rule is the player can keep entering new numbers one after another in an increasing order forever. i.e. the game ends when the player enters a number smaller than the previous number.

How do we build this? Answer: We need a new variable to store the last entered number.

Here's the logic: (NOTE: this is only the logic for the game but )

```python
### WARNING: 
### This code will not work! We still haven't done anything about EXITING the infinite loop. 
### So this code will run infintely.
n_old = 0
while True:
        n_new = int(input("Enter a new number: "))
        if n_new < n_old:
            	print("the end!")
                # somehow end the loop here.
        n_old = n_new
```

**BONUS Question:** There is one logical error with the above code. It assumes the numbers entered are greater than 0. Can you suggest a change in the code that will make it work even if the first number entered is negative.

The logic is a simple one: the loop keeps taking a new number and checks if it is smaller than the older number. **if no** it simply saves the new number in n_old for the next iteration and loop continues, **if yes**, the loop must end. Now the question comes how do we end the loop? and that is where break comes in!

<hr>

## Break Statement

With the break statement we can stop the loop anytime.

So for the above discussed example, here's how the code will look like:

```python
n_old = 0
while True:
        n_new = int(input("Enter a new number: "))
        if n_new < n_old:
            	print("the end!")
                break
        n_old = n_new
```

### Example: Searching

Problem Statement: To write a for loop to check if any of keys in the given dictionary match the search key and display the value of that key.

<iframe src="https://trinket.io/embed/python3/3ea5237952d9" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

The above solution is perfectly functional, but can we make it better?
What is the search_key is "key1"? Then it will find the key and print the value in the *first iteration* but it will continue to search for the key through the rest of the dictionary unnecessarily. So what can we do about this? Introduce break.

<iframe src="https://trinket.io/embed/python3/c72a5b3b5e83" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

<hr>

## Continue

With the continue statement we can stop the current iteration of the loop, and continue with the next.

Example: Print all numbers from 1 to n that do NOT have 2 or 3 as one of their prime factors.

One possible way to achieve this would be as follows: 

<iframe src="https://trinket.io/embed/python3/49854987512c" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

**Summary**: Inside a **for** or a **while** loop if the interpreter encouters a continue statement, it will **skip the rest of the body of the loop** and go to the next iteration.

---

That is all for this chapter! Next we shall have a look at Nested Loops!

---



