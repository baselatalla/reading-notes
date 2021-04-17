# Class-01


From Duckett HTML 

## Introduction:

> The Structure of the book are divided into three sections :

1. HTML: how to make and manage web pages structure.
2. CSS: how to control thing's positions and looking(color, size ...).
3. Practical: to help the reader to building better websites.

Browsers, Web Servers, Screen readers and Devices are ways allows people access a website. where websites are 
often written just using HTML and CSS in case of small websites or use i addition a content management system
(CMS), blogging tools, or e-commerce software in large websites.

But how the Web works ? 
Back in days when you want to make a call with a friend at first you have to call what called a 
*central office* where he is the person who will connect you with whom you want to call; it's the same approuch for the web but with a *** Domain Name System (DNS) server *** instead of the central office
which tells your browser the location of the website you e=want to vist.

##Markup
- DOCTYPES tell browsers which version of HTML you are using.
- You can add comments to your code between the < !-- and --> markers.
- The id and class attributes allow you to identify particular elements.
- The < div> and < span> elements allow you to group block-level and inline elements together.
- < iframes> cut windows into your web pages through which other pages can be displayed.
- The < meta> tag allows you to supply all kinds of information about your web page.
- Escape characters are used to include special characters in your pages such as <, >, and ©





## Structure:

 A *structure* is very important in helping readers to understand the messages you are trying to convey
and to navigate around your content so every web Page must us a *Structure* to form out the shape of it.
In a normal (and the web pages as well) documant we separate out the text to give it structure each topic 
might have a new paragraph, and each section can have a heading to describe what it covers. 

_HTML Describes the Structure of Pages_ by adding codes to the words we want to appear on the page.The HTML 
code is made up of characters that live inside angled brackets which called *HTML elements*. Elements are usually made up of two tags: 
1. opening tag "< >"
2. closing tag. "</ >"
where each HTML element tells the browser something about the information that sits between its opening and
closing tags to Describe the structure of pages.

A Closer Look at < >Tags</ >: 
Any tag included with characters in the brackets indicate the tag's purpose, EX; tages with (h1-h6) are
headlins, tages with letter (p) body words etc...

There is something tell us more about elements which calles *Attributes* provide additional information
about the contents of an element. They appear on the opening tag of the element and are made up of two parts:
a _name_ and a _value_, separated by an _equals_ sign.The attribute name indicates what kind of extra 
information you are supplying about the element's content. The value is the information or setting for the 
attribute. It should be placed in double quotes. 
Ex:
< p *lang="en-us"*>Paragraph in English </ p> - Here an attribute called lang is used to indicate the language used in this element.



## HTML5 layout

  In a traditional HTML page there are a lot of  < div > tags to gather related elements on the page such as
the a header, an article, footer or sidebar with using class or id attributes to indicate the role of the 
< div > element in the structure of the page.

![traditional](https://user-images.githubusercontent.com/55560502/109402984-0d7dbf00-7963-11eb-8bb3-ebcefd64f0b1.PNG)


_*HTML5*_ introduces a new set of elements that allow you to 
divide up the parts of a page. The names of these elements indicate the kind of content you will find in them. 

![5](https://user-images.githubusercontent.com/55560502/109402999-2c7c5100-7963-11eb-85c0-cd733c94aa12.PNG)



1. Headers < header> & Footers < footer>:
can be used for:
* The main header or footer that appears at the top or bottom of every page on the site.
* A header or footer for an individual < article> or < section> within the page.
 
2. Navigation < nav>:
The < nav> element is used to contain the major navigational blocks on the site such as the primary site 
navigation.

3. Articles < article>:
The < article> element acts asa container for any section of a page that could stand alone and potentially be 
syndicated.

4. Aside < aside>:
The < aside> element has two purposes, depending on whether it is inside an < article> element or not.
it should contain information that is related to the article but not essential to its overall meaning.

5. Sections < section>:
The < section> element groups related content together, and typically each section would have its own heading.
it may contain several distinct < article> elements that have a common theme or purpose and it can be
used to split the article up into separate sections

6. Heading Groups < hgroup>:
The purpose of the < hgroup> element is to group together a set of one or more < h1> through < h6> elements so 
that they are treated as one single heading.

7. Figures < figure> < figcaption>:
It can be used to contain any content that is referenced from the main flow of an article (not just images).
Examples of usage include:
- Images
-  Videos
- Graphs
- Diagrams
- Code samples
- Text that supports the main body of an article.

8. Sectioning Elements < div> :
The < div> element will remain an important way to group together related elements, because you should not be 
these new elements that you have just met for purposes other than those explicitly stated.



HTML5 allows web page authors to place an <a> element around a block level element that contains child 
elements. This allows you to turn an entire block into a link. This is not a new element in HTML5, but it was
not seen as a correct usage of the <a> element in earlier versions of HTML.
Older browsers that do not understand HTML5 elements need to be told which elements are block-level elements.





## Process & Design

In the process of creating a new web site there are many aspects to look after which come up as a questions
  that put the headlines and help to organize the process.Starting with (*** How is the audienes? ***) what is
  there age range, gender, location, income, hours on web, etc... which that help to understand who your 
  target audience is. Then *** Why to visit *** you need to consider why they are coming and your content and 
  design should be influenced by the goals and motivations of your users. *** what the vistors need *** First 
  you want to create a list of reasons why people would be coming to your site, then you know who is coming to 
  your site and why they are coming, so now you need to work out what information they need in order to achieve
  their goals quickly and effectively.


  * ### Site Maps

   The aim is to create a diagram of the pages that will be used to structure the site. This is known as a site
  map and it will show how those pages can be grouped. that help you decide what information should go on each 
  page, you can use a technique called card sorting.
  
  ![sitemap-template](https://user-images.githubusercontent.com/55560502/109403032-7c5b1800-7963-11eb-99c5-806e30891fa0.jpg)

  
  
  
  
  * ### WireFrames

     A wireframe is a simple sketch of the key information that needs to go on each page of a
  site. It shows the hierarchy of the information and how much space it might require.
 
 
 ![wirefram](https://user-images.githubusercontent.com/55560502/109403038-8846da00-7963-11eb-839b-9970c8001722.PNG)
 
 
 
 
 
- Getting your message across using design, the primary aim of any kind of visual design is to communicate.
 Organizing and prioritizing information on a page helps users understand its importance and what order to 
 read it in.

- Visual hierarchy, most web users do not read entire pages. Rather, they skim to find information. You can use 
contrast to create a visual hierarchy that gets across your key message and helps users find what they are 
looking for.


- Grouping and Similarity, When making sense of a design, we tend to organize visual elements into groups. 
Grouping related pieces of information together can make a design easier to comprehend. Here are some ways 
this can be achieved.


- Designing Navigation, site navigation not only helps people find where they want to go, but also helps them 
understand what your site is about and how it is organized. Good navigation tends to follow these principles...





From Duckett JS

## introduction

JavaScript allows you to make web pages more interactive by accessing and modifying the content and markup 
used in a web page while it is being viewed in the browser. You can use JavaScript to select anyelement, 
attribute, or text from an HTML page, and to add elements, attributes, and text to the page, or remove them, 
specify a set  of steps for the browser to follow (like a recipe), which allows it to access or change the 
content of a page. You can specify that a script should run when a specific  event has occurred and it could 
be run like : • A button is pressed. • A link is clicked (or tapped) on. • A cursor hovers over an element.



## The ABC of Programming

### A. What is a script and how do I create one? 

### WHAT IS A SCRIPT:
A script is a series of instructions that a computer can follow to achieve a goal. Scripts are made up of 
instructions a computer can follow step-by-step. A browser may use different parts of the script depending on 
how the user interacts with the web page. Scripts can run different sections of the code in response to the 
situation around them.

### WRITING A SCRIPT:

To write a script, you need to firststate your goal and then list the tasks that need to be completed in order
to achieve it. Start with the big picture of what you want to achieve, and break that down into smaller steps.

1. DEFINE THE GOAL
First, you need to define the task you want to achieve. You can think of this as a puzzle for the computer to 
solve.

2. DESIGN THE SCRIPT
To design a script you split the goal out into a series of tasks that are going to be involved in solving this
puzzle. This can be represented using a flowchart. You can then write down individual steps that the computer 
needs to perform in order to complete each individual task (and any information it needs to perform the task),
rather like writing a recipe that it can follow.

3. CODE EACH STEP 
Each of the steps needs to be written in a programming language that the compu ter understands. In our case, this is JavaScript.










sources :
* Jon Duckett HTML & CSS Design and Build Websites ©2011 by John Wiley & Sons, Inc., Indianapolis, Indiana
  
