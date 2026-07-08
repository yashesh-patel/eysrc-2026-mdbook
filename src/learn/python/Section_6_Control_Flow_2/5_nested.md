<h1 style="text-align: center;">Nested Loops</h1>

<hr>

A nested loop is a loop inside a loop.

The "inner loop" will be executed one time for each iteration of the "outer loop".

### Example: Chess Coordinates

Print the coordinate pairs for every square on the chess board.

<iframe src="https://trinket.io/embed/python3/235179dd3403" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

>[!NOTE] 
>The end = " " in the print function puts a space (" ") after the print instead of going to a new line.

Also note that in the above example the range() starts the sequence from 8, adds -1 (decreases by 1), and the last number is 1.

So in the above example, 
in first iteration of outer loop, i is equal to 8.
j goes through the string and prints a8 b8 c8 d8 e8 f8 g8 h8. 
Then inner loop ends.
print() statement prints nothing and goes to a new line. 
Next iteration of the outer loops starts, i = 7.
inner loop runs 8 times to print a7 b7 c7 d7 e7 f7 g7 h7.
the inner loop terminates. 
print() takes the cursor to a new line.
the outer loop continues to iterate through the next 6 rows.


### Else in For Loop

The `else` keyword in a `for` loop specifies a block of code to be executed when the loop is finished. 

#### Example 1: Without break 

<iframe src="https://trinket.io/embed/python3/fcca30ad977c" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


The `else` block will **NOT** be executed if the loop is stopped by a `break` statement.

#### Example 2: With break

<iframe src="https://trinket.io/embed/python3/63239c68abf2" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


Here, the loop stops when i is equal to 3 due to the break statement, so the else block is not executed.

---

And that is all for this section of Control Flow. In the next module we shall look briefly about function in Python!

---

