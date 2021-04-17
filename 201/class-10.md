# ERRORS HANDLING & DEBUGGING 

### ORDER OF EXECUTION

To find the source of an error, it helps to know how scripts are processed.
The order in which statements are executed can be complex; some tasks
cannot complete until another statement or function has been run.

### EXECUTIION CONTEXTS
The JavaScript interpreter uses the concept of execution contexts.
There is one global execution context; plus, each function creates a new
new execution context. They correspond to variable scope.


Every statement in a script lives in one of three execution contexts:

1. GLOBAL CONTEXT
Code that is in the script, but not in a function. There is only one global context in any page.

2. FUNCTION CONTEXT
 Code that is being run within a function. Each function has its own function context. 
 
3.EVAL CONTEXT (NOT SHOWN)
Text is executed like code in an internal function called eva l {) (which is not covered in this book).


VARIABLE SCOPE
The first two execution contexts correspond with the
notion of scope (which you met on p98):
1. GLOBAL SCOPE
If a variable is declared outside a function, it can be used anywhere because it has global scope. 
If you do not use the var keyword when creating a variable, it is placed in global scope.

2. FUNCTION-LEVEL SCOPE
When a variable is declared within a function, it can only be used within that function. This is
because it has function-level scope.


## THE STACK 
The JavaScript interpreter processes one line of code at a time. When a statement needs data from another function, it stacks (or piles) the new function on top of the current task.

When a statement has to call some other code in order to da its job, the new task goes to the top of the pile of things to do. Once the new task has been performed, the interpreter can go back to the task in hand. Each time a new item is added to the stack, it creates a new execution context. Variables defined in a function (or execution context) are only available in that function. Ifa function gets called a second time, the variables can have different values. You can see how the code that you have been looking at so far in this chapter will end up with tasks being stacked up on each other in the diagram to the right.



## EXECUTION CONTEXT & HOISTING

Each time a script enters a new execution context, there are two phases of activity:

1: PREPARE
• The new scope is created
• Variables, functions, and arguments are created
• The value of the this keyword is determined

2: EXECUTE
• Now it can assign values to variables
• Reference functions and run their code
• Execute statements


## UNDERSTANDING SCOPE

In the interpreter, each execution context has its own va ri ables object. It holds the variables, functions, and 
parameters available within it. Each execution context can also access its parent's v a ri ables object.
Functions in JavaScript are said to have lexical scope. They are linked to the object they were defined within.
So, for each execution context, the scope is the current execution context's variables object, plus the
variables object for each parent execution context.

If a variable is not found in the variables object for the current execution context, 
it can look in the variables object of the parent execution context.
But it is worth knowing that looking further up the stack can affect performance, so ideally you create
variables inside the functions that use them. If you look at the example on the left, the inner
functions can access the outer functions and their variables. For example, the greetUser() function
can access the time variable that was declared in the outer greeting() function.
Each time a function is called, it gets its own execution context and va r i ables object.

## UNDERSTANDING ERRORS

If a JavaScript statement generates an error, then it throws an exception.
At that point, the interpreter stops and looks for exception-handling code.


## ERROR OBJECTS
Error objects can help you find where your mistakes are and browsers have tools to help you read them.

When an Er ror object is created, it will contain the following properties:

<<<>>>..............................

There are seven types of built-in error objects in JavaScript. You'll see them on the next two pages:

<<<<>>>>>>>>>>>>>>>>>>>>>>>>>>>

## RROR OBJECTS CONTINUED

<<<<<<<<<<<<<<<>>>>>>>>>>>>>>>


These two pages show JavaScript's seven different types of error objects and some common examples of the kinds of errors
you are likely to see. As you can tell, the errors shown by the browsers can be rather cryptic.

<<<>>>>>>>>>

## HOW TO DEAL WITH ERRORS

1. DEBUG THE SCRIPT TO FIX ERRORS If you come across an error while writing a script (or when someone reports a bug), you will need to debug the code, track down the source of the error, and fix it.

2. HANDLE ERRORS GRACEFULLY You can handle errors gracefully using try, catch, throw, and f i na 1 ly statements.


# A DEBUGGING WORKFLOW

Debugging is about deduction: eliminating potential causes of an error. Here is a workflow for techniques you will meet over the next 20 pages. Try to narrow down where the problem might be, then look for clues.

### WHERE IS THE PROBLEM?
First, should try to can narrow down the area where
the problem seems to be. In a long script, this is
especially important.
1. Look at the error message, it tells you:
• The relevant script that caused the problem.
• The line number where it became a problem for
the interpreter. (As you will see, the cause of
the error may be earlier in a script; but this is the
point at which the script could not continue.)
• The type of error (although the underlying cause
of the error may be different).
2. Check how far the script is running.
Use tools to write messages to the console to tell
how far your script has executed.
3. Use breakpoints where things are going wrong.
They let you pause execution and inspect the va lues
that are stored in variables.

### WHAT EXACTLY IS THE PROBLEM?
Once you think that you might know the rough area
in which your problem is located, you can then try to
find the actual line of code that is causing the error.
1. When you have set breakpoints, you can see if the
variables around them have the values you would
expect them to. If not, look earlier in the script.
2. Break down I break out parts of the code to test
smaller pieces of the functionality.
• Write values of variables into the console.
• Calrfunctions from the console to check if they
are returning what you would expect them to.
• Check if objects exist and have the methods I
properties that you think they do.
3. Check the number of parameters for a function, or
the number of items in an array.
And be prepared to repeat the whole process if the
above solved one error just to uncover another ...


## STEPPING THROUGH CODE

If you set multiple breakpoints, you can step through them one-by-one to see where values
change and a problem might occur.

When you have set breakpoints, you will see that the debugger lets you step through the code
line by line and see the values or variables as your script progresses.
When you are doing this, if the debugger comes across a function, it will move onto the
next line after the function. (It does not move to where the function is defined.) This
behavior is sometimes called stepping over a function. If you want to, it is possible
to tell the debugger to step into a function to see what is happening inside the function

## THROWING ERRORS

If you know something might cause a problem for your script, you can generate your own errors
before the interpreter creates them.

Being able to throw an error at the time you know there might be a problem can be better than letting
that data cause errors further into the script. If you are working with data from a third party, you
may come across problems such as:

• JSON that contains a formatting error
• Numeric data that occasionally has a nonnumeric
value
• An error from a remote server
• A set of information with one missing value

Bad data might not cause an error in the script straight away, but it could cause a problem later on.
In such cases, it helps to report the problem straight away. It can be much harder to find the source of the
problem if the data causes an error in a different part of the script.


## DEBUGGING TIPS

Here are a selection of practical tips that you can try to use when debugging your scripts.

* ANOTHER BROWSER
Some problems are browserspecific. Try the code in another browser to see which ones are causing a problem.


* ADD NUMBERS
Write numbers to the console so you can see which the items get logged. It shows how far your
code runs before errors stop it.

* STRIP IT BACK
Remove parts of code, and strip it down to the minimum you need. You can do this either by
removing the code altogether, or by just commenting it out using multi-line comments:

/* Anything between these
characters is a cofllllent */

* EXPLAINING THE CODE
Programmers often report finding a solution to a problem while explaining the code to someone else.

* SEARCH
Stack Overflow is a Q+A site for programmers. Or use a traditional search
engine such as Google, Bing, or DuckDuckGo.

* CODE PLAYGROUNDS
If you want to ask about problematic code on a forum, in addition to pasting the code into
a post, you could add it to a code playground site (such as JSBin.com, JSFiddle. com, or
Dabbl et. corn) and then post a link to it from the forum.

