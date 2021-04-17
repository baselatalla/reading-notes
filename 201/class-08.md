# Layout

## Key Concepts in Positioning El ements

* Building Blocks
CSS treats each HTML element as if it is in its own box. This box will either be a block-level
box or an inline box. Block-level boxes start on a new line and act as the main building blocks
of any layout, while inline boxes flow between surrounding text. You can control how much space 
each box takes up by setting the width of the boxes (and sometimes the height, too). To separate 
boxes, you can use borders, margins, padding, and background colors.

- Block-level elements: start on a new line Examples include:
< h1> < p> < ul> < li>

- Inline element: flow in betweensurrounding text Examples include:
< img> < b> < i>

* Containing Elements

If one block-level element sits inside another block-level element then the outer box is
known as the containing or parent element. It is common to group a number of elements together
 inside a < div> (or other block-level) element. For example, you might group together
all of the elements that form the header of a site (such as the logo andthe main navigation).
 The < div> element that contains this group of elements is then referred to as the containing element.



## Controll ing the Position of El ements

CSS has the following positioning schemes that allow you to control
the layout of a page: normal flow, relative positioning, and absolute
positioning. You specify the positioning scheme using the position
property in CSS. You can also float elements using the float property.

1. Normal flow
Every block-level element appears on a new line, causing each item to appear lower down the page than
 the previous one. Even if you specify the width of the boxes and there is space for two elements to sit side-byside,
they will not appear next to each other. This is the default behavior (unless you tell the browser to do somethingelse)

2. Relative Positioning
This moves an element from the position it would be in normal flow, shifting it to the top, right,
bottom, or left of where it would have been placed. This does not affect the position of
surrounding elements; they stay in the position they would be in in normal flow.


3. Absolute positioning
This positions the element in relation to its containing element. It is taken out of
normal flow, meaning that it does not affect the position of any surrounding elements (as they simply ignore the
space it would have taken up). Absolutely positioned elements move as users scroll up and down the page.


To indicate where a box should be positioned, you may also need to use
box offset properties to tell the browser how far from the top or bottom
and left or right it should be placed. (You will meet these when we
introduce the positioning schemes on the following pages.)

- Fixed Positioning
This is a form of absolute positioning that positions the element in relation to the
browser window, as opposed to the containing element. Elements with fixed positioning
do not affect the position of surrounding elements and they do not move when the user
scrolls up or down the page.

- Floating Elements
Floating an element allows you to take that element out of normal flow and position
it to the far left or right of a containing box. The floated element becomes a block-level 
element around which other content can flow.


# Screen Sizes

Different visitors to your site will have different sized screens that show
different amounts of information, so your design needs to be able to
work on a range of different sized screens.

## Screen Resolution

Resolution refers to the number of dots a screen shows per inch. Some
devices have a higher resolution than desktop computers and most
operating systems allow users to adjust the resolution of their screens.
Most computers will allow owners to adjust the resolutionof the display 
or the number of pixels that are shown on the screen. For example, here you 
can see the options to change the screen size from 720 x 480
pixels up to 1280 x 800 pixels.

## Page Sizes 
Because screen sizes and display resolutions vary so much, web
designers often try to create pages of around 960-1000 pixels wide
(since most users will be able to see designs this wide on their screens).

## Fixed Width Layouts

Fixed width layout designs do not change size as the user increases
or decreases the size of their browser window. Measurements tend

1. Advantages

- Pixel values are accurate at controlling size and positioning of elements.

- The designer has far greater control over the appearance and position of items on the page than with liquid layouts.

- You can control the lengths of lines of text regardless of the size of the user's window.

- The size of an image will always remain the same relative to the rest of the page


2. Disadvantages

- You can end up with big gaps around the edge of a page.

- If the user's screen is a much higher resolution than the designer's screen, the page can                         look smaller and text can be harder to read.

- If a user increases font sizes, text might not fit into the allotted spaces.

- The design works best on devices that have a site or resolution similar to that of desktop or laptop computers.

- The page will often take up more vertical space than a liquid layout with the same content.


## Liquid Layouts

Liquid layout designs stretch and contract as the user increases or decreases the
size of their browser window. They tend tomn use percentages

1. Advantages

-  Pages expand to fill the entire browser window so there are no spaces around the page on a large screen.

- If the user has a small window, the page can contract to fit it without the user having to scroll to the side.

- The design is tolerant of users setting font sizes larger than the designer intended (because the page can). 


2. Disadvantages

- If you do not control the width of sections of the page then the design can look very different than you     intended,with unexpected gaps around certain elements or items squashed together.

- If the user has a wide window, lines of text can become very long, which makes them harder to read.

-  If the user has a very narrow window, words may be squashed and you can end up with few words on each line. 

-  If a fixed width item (such as an image) is in a box that is too small to hold it (because the user has made      the window smaller) the image can overflow over the text.


# FUNCTIONS &  METHODS

## WHAT IS A FUNCTION?

Functions let you group a series of statements together to perform a
specific task. If different parts of a script repeat the same task, you can
reuse the function (rather than repeating the same set of st atements).

## DECLARINGA FUNCTION  

To create a function, you give it a name and then write the statements needed to achieve its    
 task inside the curly braces. This is known as a function declaration.

 ![Screenshot_2](https://user-images.githubusercontent.com/55560502/109719785-d4875980-7bb1-11eb-95a8-b2ba8d5e7cbe.png)


 ## CALLING A FUNCTION
  Having declared the function, you can then execute all of the statements between its curly braces with just one line of code. This is known as calling the function.

  
  ![Screenshot_3](https://user-images.githubusercontent.com/55560502/109719798-db15d100-7bb1-11eb-84ac-505f7eb0be28.png)


  ## DECLARING FUNCTIONS
   THAT NEED INFORMATION Sometimes a function needs specific information to perform its task. In such cases, when you declare the function you give it parameters. Inside the function, the parameters act like variables.


![Screenshot_4](https://user-images.githubusercontent.com/55560502/109719826-e537cf80-7bb1-11eb-97b5-36e179ff5510.png)





# 6 Reasons for Pair Programming

1. Greater efficiency
 In reality, when two people focus on the same code base, it is easier to catch mistakes in the making. Research indicates that pair programing takes slightly longer, but produces higher-quality code that doesn’t require later effort in troubleshooting and debugging, when the pair is stuck, both programmers can research the problem and reach a solution faster. 

2. Engaged collaboration
When two programmers focus on the same code, the experience is more engaging and both programmers are more focused than if they were working alone. Another important aspect of learning to program is knowing when to ask for help. We advise our students to spend no more than fifteen minutes stuck on a problem before asking a teaching assistant or instructor for help. 


3. Learning from fellow students
Everyone has a different approach to problem solving; working with a teammate can expose developers to techniques they otherwise would not have thought of. If one developer has a unique approach to a specific problem, pair programming exposes the other developer to a new solution.

4. Social skills
Pair programming is great for improving social skills. When working with someone who has a different coding style, communication is key. This can become more difficult when two programmers have different personalities. Pair programming not only improves programming skills, but can also help programmers develop their interpersonal skills. When just grabbing the keyboard and taking over isn’t an option, getting good at finding the right words is a skill unto itself.


5. Job interview readiness
A common step in many interview processes involves pair programming between a current employee and an applicant, either in person or through a shared screen. They will carry out exercises together, such as code challenges, building a project or feature, or debugging an existing code base. By doing so, companies can get a better feel for how an applicant will fit into the team and their collaboration style.

6. Work environment readiness
Many companies that utilize pair programing expect to train fresh hires from CS-degree programs on how they operate to actually deliver a product. Code Fellows graduates who are already familiar with how pairing works can hit the ground running at a new job, with one less hurdle to overcome.