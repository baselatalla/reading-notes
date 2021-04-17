# Lists

HTML provide a three different types of lists:

1. ***Ordered lists*** are lists where each item in the list is numbered.
2. ***Unordered lists*** are lists that begin with a bullet point
3. ***Definition lists*** are made up of a set of terms along with the definitions for each of those terms


### Ordered Lists

The ordered list is created with the < ol> element.Each item in the list is placed between an opening < li> tag
and a closing < /li> tag:

< ol>
< li>Chop potatoes into quarters< /li>
< li>Simmer in salted water for 15-20 minutes until tender< /li>
< li>Heat milk, butter and nutmeg< /li>
< /ol>

### Unordered Lists

The unordered list is created with the < ul> element. also Each item in the list is placed between an opening < li> tag
and a closing < /li> tag:
< ul>
< li>1kg King Edward potatoes< /li>
< li>100ml milk< /li>
< li>50g salted butter< /li>
< /ul>


### Definition Lists 

The definition list is created with the < dl> element and usually consists of a series of terms and
their definitions. Inside the < dl> element you will usually see pairs of < dt> and < dd> elements
< dt> : This is used to contain the term being defined (the definition term).
< dd> : This is used to contain the definition.
Ex:
< dl>
< dt>Scale< /dt>
< dd>A device used to accurately measure the
weight of ingredients< /dd>
< dd>A technique by which the scales are removed
from the skin of a fish< /dd>
< /dl>

### Nested Lists

You can put a second list inside an < li> element to create a sublist or nested list.
Ex:

< ul>
< li>Mousses< /li>
< li>Pastries
< ul>
< li>Croissant< /li>
< li>Palmier< /li>
< li>Profiterole< /li>
< /ul>
< /li>
< li>Tarts< /li>
< /ul>


# Boxes

### Box Dimensions:
#### (width, height)

By default a box is sized just big enough to hold its contents. To set your _own_ dimensions for a
box you can use the **height** and **width** properties. The most popular ways to specify the size 
of a box areto use _pixels_, _percentages_, or _ems_. Traditionally, pixels have been the most popular 
method because they allow designers to accurately control their size.

### Limiting Width
#### min-width, max-width

Some page designs expand and shrink to fit the size of the user's screen. In such designs, the
min-width property specifies the smallest size a box can be displayed at when the browser
window is narrow, and the max-width property indicates the maximum width a box can
stretch to when the browser window is wide. These are very helpful propertiesto ensure that the content 
of pages are legible.


### Limiting Height
#### min-height, max-height

In the same way that you might want to limit the width of a box on a page, you may also want
to limit the height of it. This is achieved using the min-height and max-height properties.


### Overflowing Content 
#### overflow

The overflow property tells the browser what to do if the content contained within a box is larger
than the box itself. It can have one of two values:

1. hidden
This property simply hides any extra content that does not fit in the box.
2. scroll
This property adds a scrollbar to the box so that users can scroll to see the missing content.


### Border, Margin & Padding

Every box has three available properties that can be adjusted to control its appearance:

1. Every box has a border (even if it is not visible or is specified to be 0 pixels wide). The border          separates the edge of one box from another

2. Margins sit outside the edge of the border. You can set the width of a margin to create a gap between            the borders of two adjacent boxes.

3. Padding is the space between the border of a box and any content contained within it. Adding padding             can increase the readability of its contents.

### Border Width 
#### border-width

The border-width property is used to control the width of a border. The value of this property can either 
be given in pixels or using one of the following values:
* thin
* medium
* thick

### Border Style    
#### border-style

You can control the style of a border using the border-style property. This property can take
the following values:
* solid 
a single solid line 

* dotted 
a series of square dots (if your border is 2px wide, then 2px gap between each dot)

* dashed 
a series of short lines 

* double
 two solid lines (the value of the border-width property creates the sum of the two lines)

* groove
appears to be carved into the page

* ridge 
appears to stick out from the page
* inset 
appears embedded into the page

* outset
 looks like it is coming out of the screen

* hidden / none 
 border is 
 
You can individually change the styles of different borders using:

* border-top-style
* border-left-style
* border-right-style
* border-bottom-style

### Border Color
#### border-color

You can specify the color of a border using either RGB values, hex codes or CSS color names
(as you saw on pages 251-252). It is possible to individually control the colors of the borders
on different sides of a box using:

* border-top-color
* border-right-color
* border-bottom-color
* border-left-color

### Shorthand
#### border

The border property allows you to specify the width, style and color of a border in one property
(and the values should be coded in that specific order).

### PADDING
#### padding 

The padding property allows you to specify how much space should appear between the
content of an element and its border.
The value of this property is most often specified in pixels (although it is also possible to
use percentages or ems). If a percentage is used, the padding is a percentage of the browser
window (or of the containing box if it is inside another box)


### MARGIN
#### margin

The margin property controls the gap between boxes. Its value is commonly given in pixels,
although you may also use percentages or ems. If one box sits on top of another,
margins are collapsed , which means the larger of the two margins will be used and the
smaller will be disregarded.

### Centering Content

If you want to center a box on the page (or center it inside the element that it sits in), you
can set the left-margin and right-margin to auto.
In order to center a box on the page, you need to set a width for the box (otherwise it will take
up the full width of the page).

### Change Inline/Block
### display

The display property allows you to turn an inline element into a block-level element or vice versa, 
and can also be used to hide an element from the page.
The values this property can take are:

* inline
This causes a block-level element to act like an inline element.

* block
This causes an inline element to act like a block-level element.

* inline-block
This causes a block-level element to flow like an inline element, while retaining other features
 of a block-level element.

* none
This hides an element from the page. In this case, the element acts as though it is not on the
page at all (although a user could still see the content of the box if they used the view source option
in their browser).

### Hiding Boxes
#### visibility

The visibility property allows you to hide boxes from users but It leaves a space where the
element would have been. This property can take two values:
* hidden
This hides the element.

* visible
This shows the element.

If the visibility of an element is set to hidden, a blank space will appear in its place.




# ARRAYS

An array is a special type of variable. It doesn't just store one value; it stores a list of values.
using an array whenever working with a list or a set of values that are related to each other.

### CREATING AN ARRAY

we can create an array and give it a name just like you would any other variable (using the var
keyword followed by the name of the array
The values are assigned to the array inside a pair of square brackets, and each value is
separated by a comma. The values in the array do not need to be the same data type, so you
can store a string, a number and a Boolean all in the same array.
Ex:
var colors;
colors = ['white', 'black', ' custom '];


### VALUES IN ARRAYS

Values in an array are accessed as if they are in a numbered list. It is important to know that the
numbering of this list starts at zero (not one).

* NUMBERING ITEMS IN AN ARRAY
Each item in an array is automatically given a number called an index. This can be used
to access specific items in the array.Confusingly, index values start at 0 (not 1),

* ACCESSING ITEMS IN AN ARRAY
To retrieve the third item on the list, the array name is specified along with the index number in
square brackets. Here you can see a variable called i temThree is declared. Its value is set to be the third
color from the co 1 ors array.

var itemThr ee;
itemThree = col ors [ 2] ;

* NUMBER OF ITEMS IN AN ARRAY
Each array has a property calledlength, which holds the number of items in the array.
Below you can see that a variable called numCo 1 ors is declared. Its value is set to be the number of
the items in the array. The name of the array is followed by a period symbol (or full stop) which is then followed
by the 1 ength keyword. 

var numColors ; 
numColors =col ors. length;

### ACCESSING & CHANGING VALUES IN AN ARRAY

The first lines of code on the left create an array containing a list of three colors. (The values can
be added on the same line or on separate lines as shown here.) Having created the array, the
item on the list is changed from 'custom' to 'beige'. To access a value from an array,
after the array name you specify the index number for that value inside square brackets.
You can change the value of an item an array by selecting it and assigning it a new value just as
you would any other variable (using the equals sign and the new value for that item).
In the last two statements, the newly updated third item in the array is added to the page.


## USING IF ... ELSE STATEMENTS

Here you can see that an if ... e 1 se statement al lows you to provide two sets of code:
1. one set if the condition evaluates to true

2. another set if the condition is false

if (score >= pass) {
msg = 'Congratulations, you passed!';
} else {
msg = 'Have another go!';}

## SWITCH STATEMENTS

A switch statement starts with a variable called the switch value. Each case indicates a possible
value for this variable and the code that should run if the variable matches that value.

switch (level) {
case 'O ne ':
title= 'Level 1 ' ;
break;
case 'Two':
tit 1 e = ' Level 2 ' ;
break;
case ' Three' :
title = 'Level 3' ;
break ;
default :
title= 'Test';
break;}

* You have a default option that is run if none of the cases match.
* If a match is found, that code is run; then the break statement stops the rest of the switch statement running (providing better performance than multiple i f statements).


## USING SWITCH STATEMENTS

the purpose of the switch statement is to present the user with a different message depending on which
level they are at. The message is stored in a variable called msg.


## TYPE COERCION & WEAK TYPING

If you use a data type JavaScript did not expect, it tries to make sense of the operation rather
than report an error.JavaScript can convert data types behind the scenes to complete an operation. This is
known as type coercion. For example, a string 'l ' could be converted to a number 1 in the following 
expression:(' 1' > 0). As a result, the below expression would evaluate to true:

DATA        TYPE PURPOSE
string        Text
number        Number
Boolean       true or false
nul1          Empty value
undefined     Variable has been declared but not yet assigned a value

## TRUTHY & FALSY VALUES

Falsy values are treated as if they are fa 1 se. The table to the left shows a hi ghScore variable with
a series of va lues, all of which are falsy. Falsy values can also be treated as the number 0 .

Truthy values are treated as if they are true. Almost everything that is not in the falsy table can
be treated as if it were true. Truthy va lues can also be treated as the number 1.


# KEY LOOP CONCEPTS 

Here are three points to consider when you are working with loops. Each is illustrated in
examples on the following three pages:

* KEYWORDS
You will commonly see these two keywords used with loops:

1. break
This keyword causes the termination of the loop and tells the interpreter to go onto the
next statement of code outside of the loop

2. continue
This keyword te lls the interpreter to continue with the current iteration, and then check the
condition again.

* LOOPS & ARRAYS
Loops are very helpful when dealing with arrays if you want to run the same code for each item in the array.

* PERFORMANCE ISSUES
It is important to remember that when a browser comes across JavaScript, it will stop doing anything else until it has
processed that script.


### USING FOR LOOPS

A for loop is often used to loop through the items in an array. The total number of items in
the array is stored in a variable called arrayl ength. This number is obtained using the
l ength property of the array. There are three more variables: roundNumber holds the round of the test; msg holds
the message to display; i is the counter (declared outside the loop).

 
for (i = O; i < arraylength; i++) {

roundNumber = (i + l);
msg += 'Round ' + roundNumber + ' : ';
msg += scores[i] + '<br / >' ;
document .getElementByid( ' answer') .i nnerHTML msg;}


### USING WHILE LOOPS 

This loop will continue to run for as long as the condition in the parentheses is true. That
condition is a counter indicating that, as long as the variable i remains less than 10, the statements in the 
subsequent code block should run.

var i = l ;
var msg = ' ' ;

while (i < 10) {
msg += i + ' x 5 = ' + (i * 5) + '< br I>';
i++;
document .getEl ementByid( ' answer') . innerHTML = msg;

### USING DO WHILE LOOPS 

The key difference between a whi 1 e loop and a do whi 1 e loop is that the statements in the code block
come before the condition. This means that those statements are run once whether or not the condition is met.
If you take a look at the condition, it is checking that the value of the variable called i is
less than 1, but that variable has already been set to a value of 1

var i = l;
var msg : I I •
do {
msg += i + ' x 5 = ' + (i * 5) + '< br I>' ;s
i++;
} wh il e ( i < 1) ;
document .getEl ementByl d(' answer').innerHTML = msg;
