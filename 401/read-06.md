# How to use the Random Module in Python

## Random functions

### Randint

If we wanted a random integer, we can use the randint function Randint accepts two parameters: a lowest and a highest number. Generate integers between 1,5. The first value should be less than the second.

```python
import random
print random.randint(0, 5)

```

* This will output either 1, 2, 3, 4 or 5.
  
### Random

If you want a larger number, you can multiply it.

a random number between 0 and 100:

```py

import random
random.random() * 100

```

### Choice

Generate a random value from the sequence sequence.

```py
random.choice( ['red', 'black', 'green'] ).

```

The choice function can often be used for choosing a random element from a list.

```py
import random
myList = [2, 109, False, 10, "Lorem", 482, "Ipsum"]
random.choice(myList)

```

### Shuffle

The shuffle function, shuffles the elements in list in place, so they are in a random order.

```py

from random import shuffle
x = [[i] for i in range(10)]
shuffle(x)

```

```
Output:
# print x  gives  [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]
# of course your results will vary
```

### Randrange

Generate a randomly selected element from range(start, stop, step)

```py

random.randrange(start, stop[, step])
import random
for i in range(3):
    print random.randrange(0, 101, 5)

```

----------------------------------------------------------------------------------------------


# What is Risk Analysis in Software Testing and how to perform it?

***The probability of any unwanted incident is defined as Risk***

In Software Testing, ***risk analysis is the process of identifying the risks in applications or software that you built and prioritizing them to test***. After that, the process of assigning the level of risk is done. The categorization of the risks takes place, hence, the impact of the risk is calculated.


## Why use Risk Analysis?

In any software, using risk analysis at the beginning of a project highlights the potential problem areas. After knowing about the risk areas, it helps the developers and managers to mitigate the risks. When a test plan has been created, risks involved in testing the product are to be taken into consideration along with the possibility of the damage they may cause to your software along with solutions.

### Possible risks that could be encounter? 

1. Use of new hardware
2. Use of new technology
3. Use of new automation tool
4. The sequence of code
5. Availability of test resources for the application


### Risks that are unavoidable.

1. The time that you allocated for testing

2. A defect leakage due to the complexity or size of the application

3. Urgency from the clients to deliver the project

4. Incomplete requirements


So, you have to tackle the situation with care :


* Conduct Risk Assessment review meeting

* Use maximum resources to work on high-risk areas

* Create a Risk Assessment database for future use

* Identify and notice the risk magnitude indicators: high, medium, low.


### Risk magnitude indicators:

**High:** means the effect of the risk would be very high and non-tolerable. The company might face loss.

**Medium:** it is tolerable but not desirable. The company may suffer financially but there is a limited risk.

**Low:** it is tolerable. There lies little or no external exposure or no financial loss.


## Risk Identification

There are different sets of risks included in the risk identification process. Those are as follows:


* **Business Risks:** This risk is the most common risk associated with our topic. It is the risk that may ***come from your company or your customer, not from your project.***

* **Testing Risks:** You should be well ***acquainted*** with the ***platform you are working on, along with the software testing tools being used.***

* **Premature Release Risk:** a fair amount of knowledge to analyze the risk associated with releasing unsatisfactory or untested software is required

* **Software Risks:** You should be well ***versed*** with the risks associated with the software development process.


## The perspective of Risk Assessment

There are three perspectives of Risk Assessment:


* **Effect** – To assess risk by Effect. In case you identify a condition, event or action and try to determine its impact.

* **Cause** – To assess risk by Cause is opposite of by Effect. Initialize scanning the problem and reach to the point that could be the most probable reason behind that.

* **Likelihood** – To assess risk by Likelihood is to say that there is a probability that a requirement won’t be satisfied.


## How to perform Risk Analysis?

There are three steps:

1. Searching the risk

2. Analyzing the impact of each individual risk

3. Measures for the risk identified
