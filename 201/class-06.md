# Problem Domain 

  *John Sonmez* believes that hardest thing about programming is learning the problem domain, and how the problem dmain 
affect the whole proccess. Where a good understanding of a problem domain allows the programmer foucs on another aspects 
like the technology, and  by taking away the problem domain, or making it so trivial that it is easily understood, both of teaching and learning become much easier.

  IN why problem domains are hard, he explained that in how the real worhd is a messy place where problem domains we face 
as programmers are difficult to understand and look completely different depending on one viewpoint to another.programmers, we also are often not given complete information about the problem domain, so they don’t even have the information they need to understand it. 

  writing a code are fully dependent on understanding the proplem domain so to make programming easier, you can do one of
two things:

1. Make the problem domain easier 
By take a part of the problem and fully understand that part before expanding the problem domain.

2. Get better at understanding the problem domain  
where the best is to resist the temptation to “not waste anymore time talking” and make sure you understand a problem inside and out before you try and solve it with code. 



# WHAT IS AN OBJECT?

Objects group together a set of variables and functions to create a model
of a something you would recognize from the real world. In an object,
variables and functions take on new names.

* IN AN OBJECT: VARIABLES BECOME KNOWN AS PROPERTIES
If a variable is part of an object, it is called a property. Properties te ll us about the object, such as
the name of a hotel or the number of rooms it has. Each individual hotel might have a different name
and a different number of rooms.

* IN AN OBJECT: FUNCTIONS BECOME KNOWN AS METHODS
If a function is part of an object, it is called a method. Methods represent tasks that are associated withthe object. 
For example, you can check how many rooms are available by subtracting the number of booked rooms from the total number 
of rooms.

  Like _variables_ and named _functions_, *properties* and *methods* have a name and a value. In an object, that name
is called a *key*. An object cannot have two keys with the same name. This is because keys are used to access
their corresponding values.The value of a property can be a string, number, Boolean, array, or
even another object. The value of a *method* is always a _function_.


## CREATING AN OBJECT: LITERAL NOTATION

Literal notation is the easiest and most popular way to create objects. (There are several ways to create objects.) The object is the curly braces and their contents. The object is stored in a variable called hotel, so you would refer to it as the kotel object. Separate each key from its value using a color. Separate each property and method with a comma (but not after the lest value).

## ACCESSING AN OBJECT AND DOT NOTATION

You access the properties or methods of an object using dot notation. You can also access properties using square brackets. To access a praperty or method of an object you sse The pariod is Inowna the monber operator. The property or method on Its right isamember of the object on s lut. Here, two varlables arecreated to the name of the cbject, followed by a period, then Ehe ame of the property or method you ant to access. This is known as dot notation hold the hotal name and nmber of vacant rooms.





# Document Object Model (DOM)

The Document Object Model (DOM) specifies how browsers should create a model of an HTML
page and how JavaScript can access and update the contents of a web page while it is in the browser window.

## What is the DOM?
The Document Object Model (DOM) is a programming interface for HTML and XML documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.

A Web page is a document. This document can be either displayed in the browser window or as the HTML source. But it is the same document in both cases. The Document Object Model (DOM) represents that same document so it can be manipulated. The DOM is an object-oriented representation of the web page, which can be modified with a scripting language such as JavaScript.

The W3C DOM and WHATWG DOM standards are implemented in most modern browsers. Many browsers extend the standard, so care must be exercised when using them on the web where documents may be accessed by various browsers with different DOMs.

All of the properties, methods, and events available for manipulating and creating web pages are organized into objects (for example, the document object that represents the document itself, the table object that implements the special HTMLTableElement DOM interface for accessing HTML tables, and so forth). This documentation provides an object-by-object reference to the DOM.


## DOM and JavaScript

The short example above, like nearly all of the examples in this reference, is JavaScript. That is to say, it's written in JavaScript, but it uses the DOM to access the document and its elements. The DOM is not a programming language, but without it, the JavaScript language wouldn't have any model or notion of web pages, HTML documents, XML documents, and their component parts. Every element in a document—the document as a whole, the head, tables within the document, table headers, text within the table cells—is part of the document object model for that document, so they can all be accessed and manipulated using the DOM and a scripting language like JavaScript.

In the beginning, JavaScript and the DOM were tightly intertwined, but eventually, they evolved into separate entities. The page content is stored in the DOM and may be accessed and manipulated via JavaScript, so that we may write this approximative equation:

API = DOM + JavaScript

The DOM was designed to be independent of any particular programming language, making the structural representation of the document available from a single, consistent API. Though we focus exclusively on JavaScript in this reference documentation, implementations of the DOM can be built for any language,


## Accessing the DOM

You don't have to do anything special to begin using the DOM. Different browsers have different implementations of the DOM, and these implementations exhibit varying degrees of conformance to the actual DOM standard (a subject we try to avoid in this documentation), but every web browser uses some document object model to make web pages accessible via JavaScript.

When you create a script–whether it's inline in a < script> element or included in the web page by means of a script loading instruction–you can immediately begin using the API for the document or window elements to manipulate the document itself or to get at the children of that document, which are the various elements in the web page. Your DOM programming may be something as simple as the following, which displays an alert message by using the alert() function from the window object, or it may use more sophisticated DOM methods to actually create new content.


## Fundamental data types 


![Screenshot_11](https://user-images.githubusercontent.com/55560502/110224260-94daad80-7ee2-11eb-800b-6a62ad53d774.png)




There are also some common terminology considerations to keep in mind. It's common to refer to any Attribute node as an attribute, for example, and to refer to an array of DOM nodes as a nodeList. You'll find these terms and others to be introduced and used throughout the documentation.


## Interfaces and Objects
Many objects borrow from several different interfaces. The table object, for example, implements a specialized HTMLTableElement interface, which includes such methods as createCaption and insertRow. But since it's also an HTML element, table implements the Element interface described in the DOM Element Reference chapter. And finally, since an HTML element is also, as far as the DOM is concerned, a node in the tree of nodes that make up the object model for an HTML or XML page, the table object also implements the more basic Node interface, from which Element derive
