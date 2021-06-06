# In Tests We Trust — TDD with Python

## Unit tests and TDD?

Unit tests are some pieces of code to exercise the input, the output and the behaviour of your code. You can write them anytime you want.
But Test-Driven Development is a strategy to think (and write!) tests first.

## The freela

Imagine that a client has a website and through it he receives a lot of contacts from potential customers. After a while he realized that it is important for the business to identify the profile of consumer: age, gender, job and so on. But the website just receive the name and the email.
They hired you to identify the gender of a person based on his/her name. Luckily, there is an amazing API called Genderize.io that identifies the possible genders. And you quickly developed your API connection:

``` requests.get('https://api.genderize.io/?name=ana') ```

However the client demands you to write unit tests and you are curious about TDD. Here our journey begins!

## Baby Steps

The API is pretty straightforward and your work was almost done. But with TDD we need to think about tests first. And to be ok with the possibility of the beginning to be hard sometimes — and it’s totally fine. Really.

Important aspects about the unit test
Let’s write our first test!

```
def test_should_return_female_when_the_name_is_from_female_gender():
    detector = GenderDetector()
    expected_gender = detector.run(‘Ana’)
    assert expected_gender == ‘female’
```
There are some details to pay attention. The first one is the test name. The tests can be considered as your alive documentation. We need to be descriptive about it and to say what is expected and what we are testing. In this case we explicitly said: should return female when the name is from a female.

The test file name should follow the same name of module name. For instance, if our module is gender.py, our test name should be test_gender.py. It’s ideal to separate the tests folder from production code (the implementation) and to have something like this:

```
mymodule/
 — module.py
 — another_folder/
 — — another_module.py
tests/
 — test_module.py
 — another_folder/
 — — test_another_module.py 
```
Other thing to care about is the structure. A convention widely used is the AAA: Arrange, Act and Assert.

Arrange: you need to organize the data needed to execute that piece of code (input);

Act: here you will execute the code being tested (exercise the behaviour);

Assert: after executing the code, you will check if the result (output) is the same as you were expecting.

Now you can execute the tests. I suggest the lib pytest to do it. But you are free to choose anything you like.
Yay! We have our first test. It’s beautiful but it fails. And that is awesome!




## The Cycle


I hope at this time you didn’t give up of this text because this is an example of an important thing about TDD: the cycle.
The cycle is made by three steps:

The cycle is made by three steps:

🆘 Write a unit test and make it fail (it needs to fail because the feature isn’t there, right? If this test passes, call the Ghostbusters, really)

✅ Write the feature and make the test pass! (you can dance after that)

🔵 Refactor the code — the first version doesn’t need to be the beautiful one (don’t be shy) 

Using baby steps you can go through this cycle every time you add or modify a new feature in your code.

And talking about feature… let’s do the cycle!
We made our test fail. Awesome! Now it’s time to implement the feature. Thinking with baby steps, our implementation should follow the same rule, ok? So, what is needed to make this test pass? Don’t think about the whole feature, just about the test.



# Recursion

## What is Recursion? 

The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called as recursive function. Using recursive algorithm, certain problems can be solved quite easily. Examples of such problems are Towers of Hanoi (TOH), Inorder/Preorder/Postorder Tree Traversals, DFS of Graph, etc.

## A Mathematical Interpretation

Let us consider a problem that a programmer have to determine the sum of first n natural numbers, there are several ways of doing that but the simplest approach is simply add the numbers starting from 1 to n. So the function simply looks like,


approach(1) – Simply adding one by one

```
f(n) = 1 + 2 + 3 +……..+ n

but there is another mathematical approach of representing this,

pproach(2) – Recursive adding 

f(n) = 1                  n=1

f(n) = n + f(n-1)    n>1
```

There is a simple difference between the approach (1) and approach(2) and that is in approach(2) the function “ f( ) ” itself is being called inside the function, so this phenomenon is named as recursion and the function containing recursion is called recursive function, at the end this is a great tool in the hand of the programmers to code some problems in a lot easier and efficient way.

What is base condition in recursion? 
In the recursive program, the solution to the base case is provided and the solution of the bigger problem is expressed in terms of smaller problems. 

```
int fact(int n)
{
    if (n < = 1) // base case
        return 1;
    else    
        return n*fact(n-1);    
}
```

n the above example, base case for n < = 1 is defined and larger value of number can be solved by converting to smaller one till base case is reached.

How a particular problem is solved using recursion? 
The idea is to represent a problem in terms of one or more smaller problems, and add one or more base conditions that stop the recursion. For example, we compute factorial n if we know factorial of (n-1). The base case for factorial would be n = 0. We return 1 when n = 0. 

