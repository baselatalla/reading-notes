# Classes and Objects 

Objects are an encapsulation of variables and functions into a single entity. Objects get their variables and functions from classes. Classes are essentially a template to create your objects.

A very basic class would look something like this:

```py
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

```

We'll explain why you have to include that "self" as a parameter a little bit later. First, to assign the above class(template) to an object you would do the following:

```py
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

```

## Accessing Object Variables

To access the variable inside of the newly created object "myobjectx" you would do the following:

```py
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

myobjectx.variable

```

So for instance the below would output the string "blah":

```py
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

print(myobjectx.variable)


```

You can create multiple different objects that are of the same class(have the same variables and functions defined). However, each object contains independent copies of the variables defined in the class. For instance, if we were to define another object with the "MyClass" class and then change the string in the variable above:

```py
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()
myobjecty = MyClass()

myobjecty.variable = "yackity"

# Then print out both values
print(myobjectx.variable)
print(myobjecty.variable)

```

## Accessing Object Functions
To access a function inside of an object you use notation similar to accessing a variable:

```py
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

myobjectx.function()
```
The above would print out the message, "This is a message inside the class."



# Thinking Recursively in Python

## Recursive Functions in Python 

A recursive function is a function defined in terms of itself via self-referential expressions.
This means that the function will continue to call itself and repeat its behavior until some condition is met to return a result. All recursive functions share a common structure made up of two parts: base case and recursive case.

To demonstrate this structure, let’s write a recursive function for calculating n!:

1. Decompose the original problem into simpler instances of the same problem. This is the recursive case:

```

n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2 x 1
n! = n x (n−1)!

```

2. As the large problem is broken down into successively less complex ones, those subproblems must eventually become so simple that they can be solved without further subdivision. This is the base case:

```
n! = n x (n−1)! 
n! = n x (n−1) x (n−2)!
n! = n x (n−1) x (n−2) x (n−3)!
⋅
⋅
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3!
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2!
n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2 x 1!
```

Here, 1! is our base case, and it equals 1.

Recursive function for calculating n! implemented in Python:

Behind the scenes, each recursive call adds a stack frame (containing its execution context) to the call stack until we reach the base case. Then, the stack begins to unwind as each call returns its results:

![image1](https://files.realpython.com/media/stack.9c4ba62929cf.gif)


## Maintaining State 

When dealing with recursive functions, keep in mind that each recursive call has its own execution context, so to maintain state during recursion you have to either:

* Thread the state through each recursive call so that the current state is part of the current call’s execution context
* Keep the state in global scope

A demonstration should make things clearer. Let’s calculate 1 + 2 + 3 ⋅⋅⋅⋅ + 10 using recursion. The state that we have to maintain is (current number we are adding, accumulated sum till now).

Here’s how you do that by threading it through each recursive call (i.e. passing the updated current state to each recursive call as arguments):

```py

def sum_recursive(current_number, accumulated_sum):
    # Base case
    # Return the final state
    if current_number == 11:
        return accumulated_sum

    # Recursive case
    # Thread the state through the recursive call
    else:
        return sum_recursive(current_number + 1, accumulated_sum + current_number)

```

# Python Testing with pytest: Fixtures and Coverage

## Fixtures

In pytest, you define fixtures using a combination of the pytest.fixture decorator, along with a function definition. For example, say you have a file that returns a list of lines from a file, in which each line is reversed:

```py
def reverse_lines(f):
   return [one_line.rstrip()[::-1] + '\n'
           for one_line in f]

```

Note that in order to avoid the newline character from being placed at the start of the line, you remove it from the string before reversing and then add a '\n' in each returned string. Also note that although it probably would be a good idea to use a generator expression rather than a list comprehension, I'm trying to keep things relatively simple here.

If you're going to test this function, you'll need to pass it a file-like object. In my last article, I showed how you could use a StringIO object for such a thing, and that remains the case. But rather than defining global variables in your test file, you can create a fixture that'll provide your test with the appropriate object at the right time.

Here's how that looks in pytest:

```py
@pytest.fixture
def simple_file():
   return StringIO('\n'.join(['abc', 'def', 'ghi', 'jkl']))

```

On the face of it, this looks like a simple function—one that returns the value you'll want to use later. And in many ways, it's similar to what you'd get if you were to define a global variable by the name of "simple_file".

At the same time, fixtures are used differently from global variables. For example, let's say you want to include this fixture in one of your tests. You then can mention it in the test's parameter list. Then, inside the test, you can access the fixture by name. For example:

```py 
def test_reverse_lines(simple_file):
   assert reverse_lines(simple_file) == ['cba\n', 'fed\n',
 ↪'ihg\n', 'lkj\n']

```

if you set the scope of the fixture to be "module", it'll be available throughout your tests but will execute only a single time. You can do this by passing the scope parameter to the @pytest.fixture decorator:

```py

@pytest.fixture(scope='module')
def simple_file():
   return StringIO('\n'.join(['abc', 'def', 'ghi', 'jkl']))

```

Coverage
This is all great, but if you've ever done any testing, you know there's always the question of how thoroughly you have tested your code. After all, let's say you've written five functions, and that you've written tests for all of them

For example, let's assume you have a very strange function, only_odd_mul, which multiplies only odd numbers:

```py
def only_odd_mul(x, y):
   if x%2 and y%2:
       return x * y
   else:
       raise NoEvenNumbersHereException(f'{x} and/or {y}
 ↪not odd')
 ```

 Here's a test you can run on it:


```py
def test_odd_numbers():
   assert only_odd_mul(3, 5) == 15

```

There are ways in which the function could give a totally different result (for example, raise an exception) that the test didn't check.

Perhaps it's easy to see it in this example, but when software gets larger and more complex, it's not going to be so easy to eyeball it. That where you want to have "code coverage", checking that your tests have run all of the code.

