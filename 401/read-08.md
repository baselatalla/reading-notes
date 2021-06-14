## List Comprehensions

It consists of brackets containing an expression followed by a for clause, then
zero or more for or if clauses. The expressions can be anything, meaning you can
put in all kinds of objects in lists.
anything, meaning you can put in all kinds of objects in lists.
* The result will be a new list resulting from evaluating the expression in the context of the for and if clauses which follow it.
* Ex :` new_list = [expression(i) for i in old_list if filter(i)]`
* The list comprehension starts with a `'[' and ']'`, square brackets, to help you remember that the result is going to be a list.
* The basic syntax uses square brackets : `[ expression for item in list if conditional ]`
* ` new_list` : The new list (result).
* `expression(i)` : Expression is based on the variable used for each element in the old list.
* `for i in old_list` : The word for followed by the variable name to use, followed by the word in the old list
* `if filter(i)` : Apply a filter with an If-statement.
 * `new_range `= [i * i for i in range(5) if i % 2 == 0]
Which corresponds to:

*result* = [*transform* *iteration* *filter* ]

The * operator is used to repeat. The filter part answers the question if the
item should be transformed.
Using list comprehension in functions
Now, let's see how we can use list comprehension in functions.


## Create a function and name it double:
```
def double(x):
  return x*2

# If you now just print that function with a value in it, it should look like this:
>>> print double(10)
20
We can easily use list comprehension on that function.
>>> [double(x) for x in range(10)]
print double
[0, 2, 4, 6, 8, 10, 12, 14, 16, 18]
# You can put in conditions:
>>> [double(x) for x in range(10) if x%2==0]
[0, 4, 8, 12, 16]
# You can add more arguments:
>>> [x+y for x in [10,30,50] for y in [20,40,60]]
[30, 50, 70, 50, 70, 90, 70, 90, 110]
```


## Conclusion
List comprehensions are a powerful tool in Python that took me a while to understand. I hope this explanation and the graphic help you to write your own list comprehensions.