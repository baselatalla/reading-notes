# Domain modeling

Domain modelingis the process of creating a conceptual model for a specific problem. And a domain model that'sarticulated 
well can verify and validate your understanding of that problem.

When modeling a single entity that'll have many instances, build self-contained objects with the same attributes and 
behaviors. Model its attributes with a constructor function that defines and initializes properties.
Model its behaviors with small methods that focus on doing one job well. Create instances using the new keyword followed
by a call to a constructor function. Store the newly created object in a variable so you can access its properties and
methods from outside. Use the this variable within methods so you can access the object's properties and methods from
inside.


# Tables 

There are several types of information that need to be displayed in a grid or table.

## What's a Table?

A table represents information in a grid format. Examples of tables include financial reports, TV
schedules, and sports results Grids allow us to understand complex data by referencing
information on two axes. Each block in the grid is referred to as a table cell. In HTML a
table is written out row by row.


## Basic Table St ructure

*< table>*
The < table> element is used to create a table. The contents of the table are written out row by row.

*< tr>*
You indicate the start of each row using the opening < tr> tag. (The tr stands for table row.)
It is followed by one or more < td> elements (one for each cell in that row).
At the end of the row you use a closing *< /tr>* tag.

*< td>*
Each cell of a table is represented using a *< td>* element. (The td stands for table data.) At the end of each cell you 
use a closing *< /td>* tag.


## Table Headings

*< th>*

The *< th>* element is used just like the *< td>* element but its purpose is to represent the heading for either a column
or a row. (The th stands for table heading.) Even if a cell has no content, you should still use a *< td>* or
*< th>* element to represent the presence of an empty cell otherwise the table will not render correctly. (The first cell
in the first row of this example shows an empty cell.) Using *< th>* elements for headings helps people who
use screen readers, improves the ability for search engines to index your pages, and also enables you to control the
appearance of tables better when you start to use CSS.



## Spanning ColumnS

Sometimes you may need the entries in a table to stretch across more than one column.
The colspan attribute can be used on a *< th>* or *< td>*element and indicates how many columns
that cell should run across. In the example on the right you can see a timetable with
five columns; the first column contains the heading for that row (the day), the remaining four
represent one hour time slots.


## Spanning Rows

You may also need entries in a table to stretch down across more than one row.
The rowspan attribute can be used on a *< th>* or *< td>* element to indicate how many rows a cell
should span down the table.


## Long Tables

There are three elements that help distinguish between the main content of the table and
the first and last rows (which can contain different content). These elements help people
who use screen readers and also allow you to style these sections in a different manner than the
rest of the table (as you will see when you learn about CSS).

*< thead>*
The headings of the table should sit inside the *< thead>* element.

*< tbody>*
The body should sit inside the *< tbody>* element.

*< tfoot>*
The footer belongs inside the *< tfoot>* element.


## CREATING AN OBJECT: CONSTRUCTOR NOTATION

 The new keyword and the object constructor create a blank object. You can then add properties and methods to the object. First, you create a new object using a combination of the new keyword and the Object() constructor function. (This function is part of the JavaScript language and is used to create objects.) Next, having created the blank object, you can add properlies and methods to it using dot notation. Each statement that adds aproperty or method should end with a semicolon.


## UPDATING AN OBJECT 

To update the value of properties, use dot notation or square brackets. They work on objects created using literal or constructor notation. To delete a property, use the delete keyword. To updatea property, use the seme technique that wa shown on the left-hand page te add properties to the object, bt giveRanew value the object does mat have the propertype bying toupdate Rll beadded to the object.


## CREATING MANY OBJECTS:

CONSTRUCTOR NOTATION Sometimes you will want several objects to represent similar things. Object constructors can use a function as a template for creating objects. First, create the template with the object's properties and methods. A luncion called utel wilbeed as a terplate for creating new objects that represert hotats. Like functions, R contais statements. In this case sor methods to the object. TheJunction has three parameters.Eachoneet the halue of a property in the object. The methods wilbe the same tfor ach obect otedg the function they added.

## THIS (IT IS A KEYWORD) 

The keyword this is commonly used inside functions and objects. Where the function is declared alters what this means. It 
always refers to one object, usually the object in which the function operates.

A FUNCTION IN GLOBAL SCOPE
When a function is created at the top level of a script (that is, not inside another object or function), then it is in
the global scope or global context. The default object in this context is the window object. so when this is used 
inside a function in the global context it refers to the window object.

* GLOBAL VARIABLES
All global variables also become properties of the window object. so when a function is in the global
context, you can access global variables using the window object, as well as its other properties.


* A METHOD OF AN OBJECT
When a function is defined inside an object, it becomes a method. In a method, this refers to the
containing object.

* FUNCTION EXPRESSION AS METHOD
If a named function has been defined in global scope, and it is then used as a method of an object,
this refers to the object it is contained within.


## THE BROWSER OBJECT MODEL: THE WINDOW OBJECT
The window object represents the current browser window or tab. It is the topmost object in the Browser Object Model, and 
it contains other objects that tell you about the browser. Here are a selection of the window object's properties and
methods. You can also see some properties of the screen and hi story objects (which are children of the window object).


![Screenshot_6](https://user-images.githubusercontent.com/55560502/110258309-a4bdc480-7faa-11eb-939f-217531a6a63d.png)



## USING THE BROWSER OBJECT MODEL

Here, data about the browser is col lected from the window object and its children, stored in the msg
variable, and shown in the page. The+= operator adds data onto the end of the msg variable.

1. Two of the window object's
properties, i nnerWi dth and i nnerHei ght, show width and height of the browser window. JAVASCRIPT


2. Child objects are stored as
properties of t heir parent object. So dot notation is used to access them, just like you would access
any other property of that object. In turn, to access the properties of the child object, another dot is
used between the chi ld object's name and its properties, e.g., window. history . length


3. The element whose id
attribute has a value of info is selected, and the message that has been built up to this point is
written into the page.



## THE DOCUMENT OBJECT MODEL: THE DOCUMENT OBJECT

The topmost object in the Document Object Model (or DOM) is the document object. It represents the web page loaded into 
the current browser window or tab.



![Screenshot_7](https://user-images.githubusercontent.com/55560502/110258319-af785980-7faa-11eb-8ef9-08d14a0d68d4.png)



## USING THE DOCUMENT OBJECT

1. The details about the page are
collected from properties of the document object. JAVASCRIPT These details are stored inside
a variable called msg, along with HTML markup to display the information. Again, the +=
operator adds the new value onto the existing content of the msg variable.

2. You have seen the document
object's get El ementByid () method in several examples so far. It selects an element from
the page using the value of its id attribute. You will see this method in more depth on p195.


## GLOBAL OBJECTS: STRING OBJECT
Whenever you have a value that is a string, you can use the properties
and methods of the String object on that valu e. This example stores the
phrase "Home sweet home " in a variable.


![Screenshot_8](https://user-images.githubusercontent.com/55560502/110258325-b69f6780-7faa-11eb-9025-8599d12a6faf.png)



## CREATING AN INSTANCE OF THE DATE OBJECT

In order to work with dates, you create an instance of the Date object. You can then specify the time and date that you 
want it to represent. To create a Date object, use the Date() object constructor. The syntax is the same for creating any 
object with a constructor function . You can useit to create more than one Date object. By delault, when you create a 
Date object it will hold today's date and the current time. If you want it to store another date, you must explicitly 
specify the date and time you want it to hold.


## GLOBAL OBJECTS: DATE OBJECT (AND TIME)

Once you have created a Date object, the following methods let you set and retrieve the time and date that it represents.


![Screenshot_9](https://user-images.githubusercontent.com/55560502/110258336-c28b2980-7faa-11eb-9bf9-932d37e7c755.png)



