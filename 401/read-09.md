# Enriching Your Python Classes With Dunder (Magic, Special) Methods

What Are Dunder Methods?
In Python, special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores, for example __init__ or __str__.

As it quickly became tiresome to say under-under-method-under-under Pythonistas adopted the term “dunder methods”, a short form of “double under.”

These “dunders” or “special methods” in Python are also sometimes called “magic methods.” But using this terminology can make them seem more complicated than they really are—at the end of the day there’s nothing “magical” about them. You should treat these methods like a normal language feature.

Dunder methods let you emulate the behavior of built-in types. For example, to get the length of a string you can call len('string'). But an empty class definition doesn’t support this behavior out of the box:


```py
class NoLenSupport:
    pass

>>> obj = NoLenSupport()
>>> len(obj)
TypeError: "object of type 'NoLenSupport' has no len()"
```

To fix this, you can add a __len__ dunder method to your class:

```py
class LenSupport:
    def __len__(self):
        return 42

>>> obj = LenSupport()
>>> len(obj)
42
```


Another example is slicing. You can implement a __getitem__ method which allows you to use Python’s list slicing syntax: obj[start:stop].

# Special Methods and the Python Data Model

This elegant design is known as the Python data model and lets developers tap into rich language features like sequences, iteration, operator overloading, attribute access, etc.

You can see Python’s data model as a powerful API you can interface with by implementing one or more dunder methods. If you want to write more Pythonic code, knowing how and when to use dunder methods is an important step.

For a beginner this might be slightly overwhelming at first though. No worries, in this article I will guide you through the use of dunder methods using a simple Account class as an example.

Enriching a Simple Account Class
Throughout this article I will enrich a simple Python class with various dunder methods to unlock the following language features:

# Initialization of new objects

Object representation
Enable iteration
Operator overloading (comparison)
Operator overloading (addition)
Method invocation
Context manager support (with statement)
You can find the final code example here. I’ve also put together a Jupyter notebook so you can more easily play with the examples.


# Object Initialization: __init__ :

Right upon starting my class I already need a special method. To construct account objects from the Account class I need a constructor which in Python is the __init__ dunder:

```py
class Account:
    """A simple account class"""

    def __init__(self, owner, amount=0):
        """
        This is the constructor that lets us create
        objects from this class
        """
        self.owner = owner
        self.amount = amount
        self._transactions = []
```

# Object Representation: __str__, __repr__:



It’s common practice in Python to provide a string representation of your object for the consumer of your class (a bit like API documentation.) There are two ways to do this using dunder methods:

__repr__: The “official” string representation of an object. This is how you would make an object of the class. The goal of __repr__ is to be unambiguous.

__str__: The “informal” or nicely printable string representation of an object. This is for the enduser.

Let’s implement these two methods on the Account class:

```py
class Account:
    # ... (see above)

    def __repr__(self):
        return 'Account({!r}, {!r})'.format(self.owner, self.amount)

    def __str__(self):
        return 'Account of {} with starting amount: {}'.format(
            self.owner, self.amount)

```

If you don’t want to hardcode "Account" as the name for the class you can also use self.__class__.__name__ to access it programmatically.

If you wanted to implement just one of these to-string methods on a Python class, make sure it’s __repr__.

Now I can query the object in various ways and always get a nice string representation:

```py
>>> str(acc)
'Account of bob with starting amount: 10'

>>> print(acc)
"Account of bob with starting amount: 10"

>>> repr(acc)
"Account('bob', 10)"
```


# Iteration: __len__, __getitem__, __reversed__
In order to iterate over our account object I need to add some transactions. So first, I’ll define a simple method to add transactions. I’ll keep it simple because this is just setup code to explain dunder methods, and not a production-ready accounting system:

```py
def add_transaction(self, amount):
    if not isinstance(amount, int):
        raise ValueError('please use int for amount')
    self._transactions.append(amount)
```

I also defined a property to calculate the balance on the account so I can conveniently access it with account.balance. This method takes the start amount and adds a sum of all the transactions:

```py
@property
def balance(self):
    return self.amount + sum(self._transactions)
```

---------------------------------------------------------------------------





# Tutorial: Basic Statistics in Python — Probability




When studying statistics for data science, you will inevitably have to learn about probability. It is easy lose yourself in the formulas and theory behind probability, but it has essential uses in both working and daily life. We’ve previously discussed some basic concepts in descriptive statistics; now we’ll explore how statistics relates to probability.

# Prerequisites:
Similar to the previous post, this article assumes no prior knowledge of statistics, but does require at least a general knowledge of Python and general data science worflows. If you are uncomfortable with for loops and lists, I recommend covering them briefly in our introductory Python course before progressing.

# What is probability?
At the most basic level, probability seeks to answer the question, “What is the chance of an event happening?” An event is some outcome of interest. To calculate the chance of an event happening, we also need to consider all the other events that can occur. The quintessential representation of probability is the humble coin toss. In a coin toss the only events that can happen are:

* Flipping a heads
* Flipping a tails

These two events form the sample space, the set of all possible events that can happen. To calculate the probability of an event occurring, we count how many times are event of interest can occur (say flipping heads) and dividing it by the sample space. Thus, probability will tell us that an ideal coin will have a 1-in-2 chance of being heads or tails. By looking at the events that can occur, probability gives us a framework for making predictions about how often events will happen. However, even though it seems obvious, if we actually try to toss some coins, we’re likely to get an abnormally high or low counts of heads every once in a while. If we don’t want to make the assumption that the coin is fair, what can we do? We can gather data! We can use statistics to calculate probabilities based on observations from the real world and check how it compares to the ideal.

# From statistics to probability
Our data will be generated by flipping a coin 10 times and counting how many times we get heads. We will call a set of 10 coin tosses a trial. Our data point will be the number of heads we observe. We may not get the “ideal” 5 heads, but we won’t worry too much since one trial is only one data point. If we perform many, many trials, we expect the average number of heads over all of our trials to approach the 50%. The code below simulates 10, 100, 1000, and 1000000 trials, and then calculates the average proportion of heads observed. Our process is summarized in the image below as well.


![image1](https://i.imgur.com/GtbawRt.jpg)

```py 
import random
def coin_trial():
heads = 0
for i in range(100):
    if random.random() <= 0.5:
        heads +=1
    return heads
def simulate(n):
    trials = []
    for i in range(n):
        trials.append(coin_trial())
    return(sum(trials)/n)
simulate(10)
>>> 5.4
simulate(100)
>>> 4.83
simulate(1000)
>>> 5.055
simulate(1000000)
>>> 4.999781

```

The coin_trial function is what represents a simulation of 10 coin tosses. It uses the random() function to generate a float between 0 and 1, and increments our heads count if it’s within half of that range. Then, simulate repeats these trials depending on how many times you’d like, returning the average number of heads across all of the trials. The coin toss simulations give us some interesting results.

First, the data confirm that our average number of heads does approach what probability suggests it should be. Furthermore, this average improves with more trials. In 10 trials, there’s some slight error, but this error almost disappears entirely with 1,000,000 trials. As we get more trials, the deviation away from the average decreases. Sound familiar? Sure, we could have flipped the coin ourselves, but Python saves us a lot of time by allowing us to model this process in code. As we get more and more data, the real-world starts to resemble the ideal.

Thus, given enough data, statistics enables us to calculate probabilities using real-world observations. Probability provides the theory, while statistics provides the tools to test that theory using data. The descriptive statistics, specifically mean and standard deviation, become the proxies for the theoretical. You may ask, “Why would I need a proxy if I can just calculate the theoretical probability itself?” Coin tosses are a simple toy example, but the more interesting probabilities are not so easily calculated.

What is the chance of someone developing a disease over time? What is the probability that a critical car component will fail when you are driving? There are no easy ways to calculate probabilities, so we must fall back on using data and statistics to calculate them. Given more and more data, we can become more confident that what we calculate represents the true probability of these important events happening. That being said, remember from our previous statistics post that you are a sommelier-in-training. You need to figure out which wines are better than others before you start purchasing them. You have a lot of data on hand, so we’ll use our statistics to guide our decision.

## The data and the distribution
Before we can tackle the question of “which wine is better than average,” we have to mind the nature of our data. Intuitively, we’d like to use the scores of the wines to compare groups, but there comes a problem: the scores usually fall in a range. How do we compare groups of scores between types of wines and know with some degree of certainty that one is better than the other? Enter the normal distribution. The normal distribution refers to a particularly important phenomenon in the realm of probability and statistics. The normal distribution looks like this:

![image2](https://i.imgur.com/3vDS2Au.png)

The most important qualities to notice about the normal distribution is its symmetry and its shape. We’ve been calling it a distribution, but what exactly is being distributed? It depends on the context. In probability, the normal distribution is a particular distribution of the probability across all of the events. The x-axis takes on the values of events we want to know the probability of. The y-axis is the probability associated with each event, from 0 to 1.

We haven’t discussed probability distributions in-depth here, but know that the normal distribution is a particularly important kind of probability distribution. In statistics, it is the values of our data that are being distributed. Here, the x-axis is the values of our data, and the y-axis is the count of each of these values. Here’s the same picture of the normal distribution, but labelled according to a probability and statistical context:

![image3](https://i.imgur.com/egqrj58.jpg)




Tutorial: Basic Statistics in Python — Probability
Published: July 18, 2018
When studying statistics for data science, you will inevitably have to learn about probability. It is easy lose yourself in the formulas and theory behind probability, but it has essential uses in both working and daily life. We’ve previously discussed some basic concepts in descriptive statistics; now we’ll explore how statistics relates to probability.

Prerequisites:
Similar to the previous post, this article assumes no prior knowledge of statistics, but does require at least a general knowledge of Python and general data science worflows. If you are uncomfortable with for loops and lists, I recommend covering them briefly in our introductory Python course before progressing.

What is probability?
At the most basic level, probability seeks to answer the question, “What is the chance of an event happening?” An event is some outcome of interest. To calculate the chance of an event happening, we also need to consider all the other events that can occur. The quintessential representation of probability is the humble coin toss. In a coin toss the only events that can happen are:

Flipping a heads
Flipping a tails
These two events form the sample space, the set of all possible events that can happen. To calculate the probability of an event occurring, we count how many times are event of interest can occur (say flipping heads) and dividing it by the sample space. Thus, probability will tell us that an ideal coin will have a 1-in-2 chance of being heads or tails. By looking at the events that can occur, probability gives us a framework for making predictions about how often events will happen. However, even though it seems obvious, if we actually try to toss some coins, we’re likely to get an abnormally high or low counts of heads every once in a while. If we don’t want to make the assumption that the coin is fair, what can we do? We can gather data! We can use statistics to calculate probabilities based on observations from the real world and check how it compares to the ideal.

From statistics to probability
Our data will be generated by flipping a coin 10 times and counting how many times we get heads. We will call a set of 10 coin tosses a trial. Our data point will be the number of heads we observe. We may not get the “ideal” 5 heads, but we won’t worry too much since one trial is only one data point. If we perform many, many trials, we expect the average number of heads over all of our trials to approach the 50%. The code below simulates 10, 100, 1000, and 1000000 trials, and then calculates the average proportion of heads observed. Our process is summarized in the image below as well.

Coin Example

import random
def coin_trial():
heads = 0
for i in range(100):
    if random.random() <= 0.5:
        heads +=1
    return heads
def simulate(n):
    trials = []
    for i in range(n):
        trials.append(coin_trial())
    return(sum(trials)/n)
simulate(10)
>>> 5.4
simulate(100)
>>> 4.83
simulate(1000)
>>> 5.055
simulate(1000000)
>>> 4.999781
The coin_trial function is what represents a simulation of 10 coin tosses. It uses the random() function to generate a float between 0 and 1, and increments our heads count if it’s within half of that range. Then, simulate repeats these trials depending on how many times you’d like, returning the average number of heads across all of the trials. The coin toss simulations give us some interesting results.

First, the data confirm that our average number of heads does approach what probability suggests it should be. Furthermore, this average improves with more trials. In 10 trials, there’s some slight error, but this error almost disappears entirely with 1,000,000 trials. As we get more trials, the deviation away from the average decreases. Sound familiar? Sure, we could have flipped the coin ourselves, but Python saves us a lot of time by allowing us to model this process in code. As we get more and more data, the real-world starts to resemble the ideal.

Thus, given enough data, statistics enables us to calculate probabilities using real-world observations. Probability provides the theory, while statistics provides the tools to test that theory using data. The descriptive statistics, specifically mean and standard deviation, become the proxies for the theoretical. You may ask, “Why would I need a proxy if I can just calculate the theoretical probability itself?” Coin tosses are a simple toy example, but the more interesting probabilities are not so easily calculated.

What is the chance of someone developing a disease over time? What is the probability that a critical car component will fail when you are driving? There are no easy ways to calculate probabilities, so we must fall back on using data and statistics to calculate them. Given more and more data, we can become more confident that what we calculate represents the true probability of these important events happening. That being said, remember from our previous statistics post that you are a sommelier-in-training. You need to figure out which wines are better than others before you start purchasing them. You have a lot of data on hand, so we’ll use our statistics to guide our decision.

The data and the distribution
Before we can tackle the question of “which wine is better than average,” we have to mind the nature of our data. Intuitively, we’d like to use the scores of the wines to compare groups, but there comes a problem: the scores usually fall in a range. How do we compare groups of scores between types of wines and know with some degree of certainty that one is better than the other? Enter the normal distribution. The normal distribution refers to a particularly important phenomenon in the realm of probability and statistics. The normal distribution looks like this: Normal Distribution Look

The most important qualities to notice about the normal distribution is its symmetry and its shape. We’ve been calling it a distribution, but what exactly is being distributed? It depends on the context. In probability, the normal distribution is a particular distribution of the probability across all of the events. The x-axis takes on the values of events we want to know the probability of. The y-axis is the probability associated with each event, from 0 to 1.

We haven’t discussed probability distributions in-depth here, but know that the normal distribution is a particularly important kind of probability distribution. In statistics, it is the values of our data that are being distributed. Here, the x-axis is the values of our data, and the y-axis is the count of each of these values. Here’s the same picture of the normal distribution, but labelled according to a probability and statistical context: Axes Comparison

In a probability context, the high point in a normal distribution represents the event with the highest probability of occurring. As you get farther away from this event on either side, the probability drops rapidly, forming that familiar bell-shape. The high point in a statistical context actually represents the mean. As in probability, as you get farther from the mean, you rapidly drop off in frequency. That is to say, extremely high and low deviations from the mean are present but exceedingly rare.

If you suspect there is another relationship between probability and statistics through the normal distribution, then you are correct in thinking so! We will explore this important relationship later in the article, so hold tight. Since we’ll be using the distribution of scores to compare different wines, we’ll do some set up to capture some wines that we’re interested in. We’ll bring in the wine data and then separate out the scores of some wines of interest to us. To bring back in the data, we need the following code:

```py 
import csv
with open("wine-data.csv", "r", encoding="latin-1") as f:
    wines = list(csv.reader(f))

```