# JQUERY

WHAT IS JQUERY? jQuery is a JavaScript file that you include in your web pages. It lets you find elements using CSS-style selectors and then do something with the elements using jQuery methods. 1: FIND ELEMENTS USING CSs-STYLE SELECTORS.

jQuery offers a simple way to achieve a variety of common JavaScript tasks quickly and consistently, across all major
browsers and without any fallback code needed.

1: FIND ELEMENTS USING CSS-STYLE SELECTORS

 A function called jQuery () lets you find one or more elements in the page. It creates an object called jQuery which holds references to those elements. $) is often used as a shorthand to save typing jQuery(), as shown here. 
 
 $('li.hot') 

  The jQuery () function has one parameter: a CSS-style selector. This selector finds all of the <l1> elements with a class of hot.

The jQuery object has many methods that you can use to work with the elements you select. The methods represent tasks that you commonly need to perform with elements.


 2: DO SOMETHING WITH THE ELEMENTS USING JQUERY
 
  METHODS Here a JQuery object is created by the Juery () function. The object and the elements It contains is referred to as amatched set or a Query selection. You can then use the methods of the jQuery object to update the elements that It contains. Here, the method adds a new valae to the class attribute METHOD JOUERY OBJECT


## Selecting Elements

1. Selecting Elements by ID
$( "#myId" ); // Note IDs must be unique per page.


2. Selecting Elements by Class Name
$( ".myClass" ); 

3. Selecting Elements by Attribute
$( "input[name='first_name']" );

4. Selecting Elements by Compound CSS Selector
$( "#contents ul.people li" );

5. Selecting Elements with a Comma-separated List of Selectors
$( "div.myClass, ul.people" );

6. Pseudo-Selectors
$( "a.external:first" );
$( "tr:odd" );
 
// Select all input-like elements in a form (more on this below).
$( "#myForm :input" );
$( "div:visible" );
 
// All except the first three divs.
$( "div:gt(2)" );
 
// All currently animated divs.
$( "div:animated" );


## DOING THINGS WITH YOUR SELECTION

The • htm 1 () and • text () methods both retrieve and update the content
of elements. This page will focus on how to retrieve element content. To
learn how to update element content.

### UPDATING ELEMENTS

Here are four methods that update the content of all elements in a jQuery selection

. html()
This method gives every element
in the matched set the same new
content. The new content may
include HTML.

. text()
This method gives every element
in the matched set the same new
text content. Any markup would
be shown as text.


.replaceWith()
This method replaces every
element in a matched set with
new content. It also returns the
replaced elements.

remove()
This method removes all of the
elements in the matched set.

### INSERTING ELEMENTS

Inserting new elements involves two steps:

1: CREATING NEW ELEMENTS IN A JQUERY OBJECT
The fo llowing statement creates a variable called $newFragment and
stores a jQuery object in it. The jQuery object is set to contain an empty

2: ADDING THE NEW ELEMENTS TO THE PAGE
Once you have a variable holding th~ new content, you can use the
following methods to add the content to the DOM tree:

.before()
This method inserts content
before the selected element(s) .

.prepend()
This method inserts content
inside the selected element(s),
after the opening tag.

.after()
This method inserts content
after the selected element (s).

.append()
This method inserts content
inside the selected element(s),
before the closing tag.



### GETTING AND SETTING ATTRIBUTE VALUES

.attr()
This method can get or set a
specified attribute and its va lue.
To get the value of an attribute,
you specify the name of the
attribute in the parentheses.

. removeAttr()
This method removes a specified
attribute (and its value). You just
specify the name of the attribute
that you want to remove from the
element in the parentheses

. addCl ass()
This method adds a new value
to the existing value of the cl ass
attribute. It does not overwrite
existing values.

.removeClass()
This method removes a value
from the cl ass attribute, leaving
any other class names within
that attribute intact.



GETTING & SETTING CSS PROPERTIES
The . css () method lets you retrieve and set the values of CSS properties


1. HOW TO GET A CSS PROPERTY

This will store the background color of the first list item in a variable
called backgroundCo l or. The color will be returned as an RGB value.
var backgroundColor = $( ' li ' ) . css( 'background-color' );

2. HOW TO SET A CSS PROPERTY

This will set the background color of all list items. Note how the CSS
property and its value are separated using a comma instead of a colon.
$( 'li ') .css( 'background- color' , '1272727' );

When dealing with dimensions that are specified in pixels. you can
increase and decrease the va lues using the+= and-= operators.
${'li ' ).css( 'padding-left', '+=20' );

3. SETTING MULTIPLE PROPERTIES

You can set multiple properties using object literal notation:
• Properties and values are placed in curly braces
• A colon is used to separate property names from their values
• A comma separates each pair (but there is not one after the last pair)
This sets the background color and typeface for all list items.
$('1 i ') .css({
' background- col or' : ' #272727' ,
' font-family' : 'Courier'
} ) ;




WORKING WITH EACH ELEMENT IN A SELECTION
jQuery allows you to recreate the functionality of a loop on a selection of elements, using the
• each () method.

• each()
Allows you to perform one or
more statements on each of
the items in the selection of
elements that is returned by a
selector - rather like a loop in
JavaScript.
It takes one parameter:
a function containing the
statements you want to run on
each element.


this or $(this)
As the . each() method goes
through the elements in a
selection, you can access the
current element using the this
keyword.
You also often see $ (thi s),
which uses the this keyword to
create a new jQuery selection
containing the current element.
It allows you to use jQuery
methods on the current element.


EVENT METHODS
The • on () method is used to handle all events. Behind the scenes, jQuery handles all of the
cross-browser issues you saw in the last chapter.

Using the . on () method is no different than using any other jQuery method; you:

• Use a selector to create a jQuery selection.
• Use . on() to indicate which event you want to respond to. It adds an event listener to each element in the selection


## LOADING JQUERY FROM A CDN
When a page loads jQuery from a CDN, you will often see a syntax like the one shown below.
It starts with a <script> tag that tries to load the jQuery file from the CDN. But note that the URL
for the script starts with two forward slashes (not http:).

LOADING JQUERY FROM A CDN
This is known as a protocol relative URL. If the user is looking at the current page through https, then they will not see an error that tells them there are unsecure items on the page. Note: This does not work locally with the f i l e:// protocol. This is often followed by a second <script> tag that contains a logical operator, which checks to see if jQuery has loaded. If it has not loaded,
the browser tries to load the jQuery script from the same server as the rest of the website.




# 6 Reasons for Pair Programming

How does pair programming work?

While there are many different styles, pair programming commonly involves two roles: the Driver and the Navigator. The Driver is the programmer who is typing and the only one whose hands are on the keyboard. Handling the “mechanics” of coding, the Driver manages the text editor, switching files, version control, and—of course writing—code. The Navigator uses their words to guide the Driver but does not provide any direct input to the computer. The Navigator thinks about the big picture, what comes next, how an algorithm might be converted in to code, while scanning for typos or bugs. The Navigator might also utilize their computer as a second screen to look up solutions and documentation, but should not be writing any code.

Why pair program?

While learning to code, developers likely study several programming languages. Similar to a foreign language class, there are four fundamental skills that help anyone learn a new language: Listening: hearing and interpreting the vocabulary Speaking: using the correct words to communicate an idea Reading: understanding what written language intends to convey Writing: producing from scratch a meaningful

Pair programming touches on all four skills: developers explain out loud what the code should do, listen to others’ guidance, read code that others have written, and write code themselves.


1. Greater efficiency

It is a common misconception that pair programming takes a lot longer and is less efficient. In reality, when two people focus on the same code base, it is easier to catch mistakes in the making. Research indicates that pair programing takes slightly longer, but produces higher-quality code that doesn’t require later effort in troubleshooting and debugging (let alone exposing users to a broken product). So, in the long-run, it’s often actually more efficient than two people working on separate features. When coming up with ideas and discussing solutions out loud, two programmers may come to a solution faster than one programmer on their own. Also, when the pair is stuck, both programmers can research the problem and reach a solution faster. Researches also identified pairing enhances technical skills, team communication, and even enjoyability of coding in the workplace.

2. Engaged collaboration

When two programmers focus on the same code, the experience is more engaging and both programmers are more focused than if they were working alone. It is harder to procrastinate or get off track when someone else is relying on you to complete the work. Popping open your Facebook timeline is just that less enticing when someone else is looking at your screen.

Another important aspect of learning to program is knowing when to ask for help. We advise our students to spend no more than fifteen minutes stuck on a problem before asking a teaching assistant or instructor for help. When developers pair program, they rely more on each other and can often find a solution together without needing to ask for additional help. Ultimately, this boosts overall confidence.

3. Learning from fellow students

Everyone has a different approach to problem solving; working with a teammate can expose developers to techniques they otherwise would not have thought of. If one developer has a unique approach to a specific problem, pair programming exposes the other developer to a new solution.

Often times, the developers in a pairing have different skill sets. If one programmer is more experienced in a certain skill, they can teach a student who is less familiar with that area. The less experienced developer benefits from the experienced developer’s knowledge and guidance, and the latter benefits from explaining the topic in their own words, further solidifying their own understanding.

4. Social skills

Pair programming is great for improving social skills. When working with someone who has a different coding style, communication is key. This can become more difficult when two programmers have different personalities. Pair programming not only improves programming skills, but can also help programmers develop their interpersonal skills. When just grabbing the keyboard and taking over isn’t an option, getting good at finding the right words is a skill unto itself.

This has long-term career impacts. As much as employers want strong programmers, they know it’s essential to hire people who can work well with others.

5. Job interview readiness

A common step in many interview processes involves pair programming between a current employee and an applicant, either in person or through a shared screen. They will carry out exercises together, such as code challenges, building a project or feature, or debugging an existing code base. By doing so, companies can get a better feel for how an applicant will fit into the team and their collaboration style.

For most roles, the ability to work with and learn from others and stellar communication skills are as (or more!) important to a company than specific technical skills. Pair programming strengthens all of those skills.

6. Work environment readiness

Many companies that utilize pair programing expect to train fresh hires from CS-degree programs on how they operate to actually deliver a product. Code Fellows graduates who are already familiar with how pairing works can hit the ground running at a new job, with one less hurdle to overcome.