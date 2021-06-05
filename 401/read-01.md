# A beginner's guide to Big O Notation

Big O notation is used in Computer Science to describe the performance or complexity of an algorithm. Big O specifically describes the worst-case scenario, and can be used to describe the execution time required or the space used (e.g. in memory or on disk) by an algorithm.

## O(1)
O(1) describes an algorithm that will always execute in the same time (or space) regardless of the size of the input data set.

## O(N)
O(N) describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set. The example below also demonstrates how Big O favours the worst-case performance scenario; a matching string could be found during any iteration of the for loop and the function would return early, but Big O notation will always assume the upper limit where the algorithm will perform the maximum number of iterations.

## O(N²)
O(N²) represents an algorithm whose performance is directly proportional to the square of the size of the input data set. This is common with algorithms that involve nested iterations over the data set. Deeper nested iterations will result in O(N³), O(N⁴) etc.

## O(2^N)
O(2^N) denotes an algorithm whose growth doubles with each addition to the input data set. The growth curve of an O(2^N) function is exponential — starting off very shallow, then rising meteorically.



# Pain vs. Suffering

All growth comes with some degree of pain, as it pulls you out of your comfort zone. The greater the growth, the greater the pain. But pain in the service of growth is a good thing, as long as that pain is what’s necessary to achieve the growth that you’re aiming for. And even better than that, this pain is only temporary. It’s what will launch you forward into the next phase of your life

As you experience pain, seek the remedy! Ask questions that bridge the gap between what you know and what you need to be able to do. Research! Build your resources and your community! Don’t experience the pain in silence—that slides toward needless pain and the realm of suffering.

Find the common thread that makes the pain worthwhile, that puts the pain into perspective. You’re here because you chose to invest in a different life. A better life.


# Python Names and Values 

Python is a very approachable language. Often it works just as you expect if you come to it from other languages. But you might suddenly encounter surprising behavior.

The underlying mechanisms of Python are often quite simple, but their combined effects might not be what you expect. By understanding the mechanisms, you can reason about their effects.

As in many programming languages, a Python assignment statement associates a symbolic name on the left-hand side with a value on the right-hand side. In Python, we say that names refer to values, or a name is a reference to a value:

```
x = 23
```

Now the name “x” refers to the value 23. The next time we use the name x, we’ll get the value 23:
```
print(x)        # prints 23
```

Another way people describe this is, x is bound to 23.

Exactly how the name refers to the value isn’t really important. If you’re experienced with the C language, you might like to think of it as a pointer, but if that means nothing to you then don’t worry about it.

To help explain what’s going on, I’ll use diagrams. A gray rectangular tag-like shape is a name, with an arrow pointing to its value. The slide shows the name x referring to an integer 23.


There’s no rule that says a value can only have one name. An assignment statement can make a second (or third, ...) name refer to the same value.

```
x = 23
y = x
```

Now x and y both refer to the same value

Neither x or y is the “real” name. They have equal status: each refers to the value in exactly the same way.

If two names refer to the same value, this doesn’t magically link the two names. Reassigning one of them won’t reassign the other also:

```
x = 23
y = x
x = 12
```

When we said “y = x”, that doesn’t mean that they will always be the same forever. Reassigning x leaves y alone. Imagine the chaos if it didn’t!

Python keeps track of how many references each value has, and automatically cleans up values that have none. This is called “garbage collection,” and means that you don’t have to get rid of values, they go away by themselves when they are no longer needed.

Exactly how Python keeps track is an implementation detail, but if you hear the term “reference counting,” that’s an important part of it. Sometimes cleaning up a value is called reclaiming it.

Also important to note is that Python has no mechanism for making a name refer to another name. That is, there is no way to make y be a permanent alias for x no matter how x is reassigned.