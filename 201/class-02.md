
# Text in HTML

In case of creating a web page, adding tags to the contents of the page are essasional in order to markup and  
provide extra meaning to the content for the browsers and to allow it to show users the appropriate structure 
for the page.

Where the markup divided into two type:

* ### Structural markup: 
the elements that you can use to describe both headings and paragraphs



1. Heading  

HTML has six "levels" of headings:
< h1> ,< h2>, < h3>, < h4>, < h5>, < h6> (largest to smallest)
< h1> is used for main headings .
< h2> is used for subheadings.
If there are further sections under the subheadings then the
< h3> element is used, and so on...

also, using the levels of headings can be to indicate the importance of the subject.



2. Paragraphs : 
To create a paragraph, surround the words that make up the paragraph with an opening < p> tag and closing
 < /p> tag. By default, a browser will show each paragraph on a new line with some space between it and any
subsequent paragraphs.



3. Bold < b> & Italic < i> : 

By enclosing words in the tags < b> and < /b> we can make characters appear bold. The < b> element also 
represents a section of text that would be presented in a visually different way (for example key words in a
paragraph) although the use of the < b> element does not imply any additional meaning.


By enclosing words in the tags < i> and < /i> we can make characters appear italic. The < i> element also 
represents a section of text that would be said in a different way from surrounding content — such as
technical terms, names of ships, foreign words, thoughts, or other terms that would usually be italicized.



4. Superscript < sup> & Subscript < sub> :

The < sup> element is used to contain characters that should be superscript such as the suffixes of dates or
mathematical concepts like raising a number to a power such as 2^2.

The < sub> element is used to contain characters that should be subscript. It is commonly used with foot notes 
or chemical formulas such as H 2 O.


5. White Space :

In order to make code easier to read, web page authors oftenadd extra spaces or start some elements on new 
lines. When the browser comes across two or more spaces next to each other, it only displays one space.
Similarly if it comes across a line break, it treats that as a single space too. This is known as white space 
collapsing. 


6. Line Breaks < br/> & Horizontal Rules < hr/> :

As you have already seen, the browser will automatically show each new paragraph or heading on a new line. But if you wanted to add a line break inside the middle of a paragraph you can use the line break tag < br />.

To create a break between themes — such as a change of topic in a book or a new scene in a play — you can add a
horizontal rule between sections using the < hr/> tag.


* ### Semantic markup: 
which provides extra information; such as where emphasis is placed in a sentence, that something you have 
written is a quotation (and who said it), the meaning of acronyms, and so on

1. Strong < strong>  & Emphasis < em> :

The use of the < strong> element indicates that its content has strong importance. For example, the words
contained in this element might be said with strong emphasis. By default, browsers will show the contents of a 
< strong> element in bold.

The < em> element indicates emphasis that subtly changes the meaning of a sentence. By default browsers will 
show the contents of an < em> element in italic.

2. Quotations :

There are two elements commonly used for marking up quotations:

The < blockquote> element is used for longer quotes that take up an entire paragraph. Note how the < p> 
element is still used inside the < blockquote> element. Browsers tend to indent the contents of the 
< blockquote>  element,

The < q> element is used for shorter quotes that sit within a paragraph. Browsers are supposed to put quotes 
around the < q> element, however Internet Explorer does not — therefore many people avoid using the 
< q> element.

3. Abbreviations & Acronyms :

If you use an abbreviation or an acronym, then the < abbr> element can be used. A title attribute on the 
opening tag is used to specify the full term.


4. Citations < cite> & Definitions < dfn> :

When you are referencing a piece of work such as a book, film or research paper, the < cite> element can be 
used to indicate where the citation is from. 

The first time you explain some new terminology (perhaps an academic concept or some jargon) in a document, it 
is known as the defining instance of it. The < dfn> element is used to indicate the defining instance of a new 
term.

5. Author Details < address> :\

The < address> element has quite a specific use: to contain contact details for the author of
the page. It can contain a physical address, but it does not have to. For example, it may also contain a
phone number or email address.

6. Changes to Content < ins> , < del> ,< s> :

The < ins> element can be used to show content that has been inserted into a document, while the < del> 
element can show text that has been deleted from it.


The < s> element indicates something that is no longer accurate or relevant (but that should not be deleted).
Visually the content of an < s> element will usually be displayed with a line through the center.


## Introducing CSS 

CSS allows us to create rules that specify how the content of an element should appear. where we can for Ex:
specify that the background of the page is cream, all paragraphs shouldappear in gray using the Arial 
typeface, or that all level one headings should be in a blue, italic, Times typeface.

* The key to understanding how CSS works is to imagine that there is an invisible box around every HTML element.

* CSS allows you to create rules that control the way that each individual box (and the contents of that box) is presented.
  
* CSS works by associating rules with HTML elements. These rules govern how the content of specified elements should be displayed. A CSS rule contains two parts: a selector and a declaration.

1. Selectors:
indicate which element the rule applies to. The same rule can apply to more than one element if you separate the element names with commas.


2. Declarations: 
indicate how the elements referred to in the selector should be styled.Declarations are split into two
parts (a property and a value), and are separated by a colon.


* CSS declarations sit inside curly brackets and each is made up of two parts: a property and a value, separated by a colon. You can specify several properties in one declaration, each separated by a semi-colon

1. Properties:
indicate the aspects of the element you want to change. For example, color, font, width, height and border.

2. Values:
specify the settings you want to use for the chosen properties. For example, if you want to specify a color
property then the value is the color you want the text in these elements to be.

### Using External CSS:

The *< link>* element can be used in an HTML document to tell the browser where to find the CSS file used to 
style the page. It is an empty element (meaning it does not need a closing tag), and it lives inside the 
*< head>* element. It should use three attributes:

1. href :
This specifies the path to the CSS file (which is often placed in a folder called css or styles).

2. type :
This attribute specifies the type of document being linked to. The value should be text/css.

3. rel
This specifies the relationship between the HTML page and the file it is linked to. The value
should be stylesheet when linking to a CSS file.



### Using Internal CSS:

You can also include CSS rules within an HTML page by placing them inside a *< style>* element, which usually 
sits inside the < head> element of the page. The < style> element should use the type attribute to indicate
that the styles are specified in CSS. The value should be text/css.


When building a site with more than one page, you should use an external CSS style sheet. This:

- Allows all pages to use the
same style rules (rather thanrepeating them in each page).
- Keeps the content separate
from how the page looks.
- Means you can change the
styles used across all pages by altering just one file (rather than each individual page).

### CSS Selectors :

 There are many different types of CSS selector that allow you to target rules to specific elements in an HTML
 document. The table on the opposite page introduces the most commonly used CSS selectors. On this page, there 
 is an HTML file to demonstrate which elements these CSS selectors would apply to. CSS selectors are case 
 sensitive, so they must match element names and attribute values exactly.

![Capture](https://user-images.githubusercontent.com/55560502/109437329-0622e800-7a2d-11eb-93a3-16a2c2f84c3d.PNG)






## Basic javaScript instracutions

 1. STATEMENTS:

A script is a series of instructions that a computer can follow one-by-one. Each individual instruction or step is known as a statement. Statements should end with
 a semicolon.notes that :

1. Each of the lines of code in green is a statement.
2. The pink curly braces indicate the start and endof a code block. (Each code block could contain many more statements.)
3. JAVASCRIPT IS CASE SENSITIVE.
2. STATEMENTS ARE INSTRUCTIONS AND EACH ONE STARTS ON A NEW LINE.
3. STATEMENTS CAN BE ORGANIZED INTO CODE BLOCKS. 


2. COMMENTS:

You should write comments to explain what your code does. They help make your code easier to read and understand. This can help you and others who read your code.
like:
 
1./* Th i s script displays a greeting to the user based upon the current time. It is an example from JavaScript & jQuer y book */  (mulyi line comments)
2. // Create a ne1~ dat e object (one line comment)



3. VARIABLES:
A variable is a good name for this concept because the data stored in a variable can change (or vary) each time a script runs. The use of variables to 
represent numbers or other kinds of data .



 * HOW TO DECLARE VARIABLES:

to use a variable , you need to announce that you want to use it.this involves creating a variable and giving it a name 



* HOw TO ASSAIGN THEM A VALUE :

In JS the equal sign (=) is an assignment operater, it says that you are going to assign a value to the  variable ( X = 4;).

3. DATA TYPES:

JavaScript distinguishes between numbers, strings, and true or false values known as Booleans. 

1. NUMERIC DATA TYPE :
For tasks that involve counting or calculating sums, you will use numbers 0-9 (22).

2. STRING DATA TYPE:
The strings data type consists ofletters and other characters.('yooyoo').

3. BOOLEAN DATA TYPE
Boolean data types can have one of two values: true or false.


## RULES FOR NAMING VARIABLES

1. The name must begin with a letter, dollar sign ($),or an underscore (_). It must not start with a number.

2. The name can contain letters,numbers, dollar sign ($), or an underscore (_). Note that you must not use a dash(-) or a period (.) in a variable name.

3. You cannot use keywords or reserved words. Keywords are special words that tell the interpreter to dosomething. For example, var is a keyword used to declare a variable. Reservedwords are ones that may be used in a future version of JavaScript.

4. All variables are case sensitive, so score and Score would be different variable names, but it is bad practice to create two variables that have the same name using different cases.


5. Use a name that describes the kind of information that the variable stores. For example, fi rstName might be used to store a person's first name, l astNarne for their last name, and age for their age.



## ARRAYS

An array is a special type of variable. It doesn't just store one value; it stores a list of values.
Arrays are especially helpful when you do not know how many items a list will contain because, when you create the array, you do not need to specify how many values it will hold

## EXPRESSIONS

An expression evaluates into (results in) a single value. Broadly speaking there are two types of expressions.
1. EXPRESSIONS THAT JUST ASSIGN A VALUE TO A VARIABLE
2. EXPRESSIONS THAT USE TWO OR MORE VALUES TO RETURN A SINGLE VALUE


## OPERATORS

Expressions rely on things called operators; they allow programmers to create a single value from one or more values.

1. ARITHMETIC OPERATORS
JavaScript contains the following mathematical operators, which you can use with numbers. You may remember some from math class.


![Capture2](https://user-images.githubusercontent.com/55560502/109458007-a7796080-7a64-11eb-9e90-20516fe87379.PNG)


2. STRING OPERATOR 
There is just one string operator: the+ symbol. It is used to join the strings on either side of it
 MIXING NUMBERS AND STRINGS TOGETHER


## DECISIONS & loops

### if Statement

Use the if statement to specify a block of JavaScript code to be executed if a condition is true
if (condition) {
  //  block of code to be executed if the condition is true
}

  Use the else statement to specify a block of code to be executed if the condition is false

if (condition) {
  //  block of code to be executed if the condition is true
} else {
  //  block of code to be executed if the condition is false
}

 ### SWITCH STATEMENTS
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



## To Write a Git Commit Message Commit messages matte:
The seven rules of a great Git commit message Keep in mind:
 This has all been said before.
1. Separate subject from body with a blank line
2. Limit the subject line to 50 characters
3. Capitalize the subject line
4. Do not end the subject line with a period
5. Use the imperative mood in the subject line
6. Wrap the body at 72 characters
7. Use the body to explain what and why vs. how

 sources :

<<<<<<< HEAD
 ## Basic javaScript instracutions

 1. STATEMENTS:

A script is a series of instructions that a computer can follow one-by-one. Each individual instruction or step is known as a statement. Statements should end with
 a semicolon.notes that :

1. Each of the lines of code in green is a statement.
2. The pink curly braces indicate the start and endof a code block. (Each code block could contain many more statements.)
3. JAVASCRIPT IS CASE SENSITIVE.
2. STATEMENTS ARE INSTRUCTIONS AND EACH ONE STARTS ON A NEW LINE.
3. STATEMENTS CAN BE ORGANIZED INTO CODE BLOCKS. 


2. COMMENTS:

You should write comments to explain what your code does. They help make your code easier to read and understand. This can help you and others who read your code.
like:
 
1./* Th i s script displays a greeting to the user based upon the current time. It is an example from JavaScript & jQuer y book */  (mulyi line comments)
2. // Create a ne1~ dat e object (one line comment)



3. VARIABLES:
A variable is a good name for this concept because the data stored in a variable can change (or vary) each time a script runs. The use of variables to 
represent numbers or other kinds of data .



 * HOW TO DECLARE VARIABLES:

to use a variable , you need to announce that you want to use it.this involves creating a variable and giving it a name 



* HOw TO ASSAIGN THEM A VALUE :

In JS the equal sign (=) is an assignment operater, it says that you are going to assign a value to the  variable ( X = 4;).

3. DATA TYPES:

JavaScript distinguishes between numbers, strings, and true or false values known as Booleans. 

1. NUMERIC DATA TYPE :
For tasks that involve counting or calculating sums, you will use numbers 0-9 (22).

2. STRING DATA TYPE:
The strings data type consists ofletters and other characters.('yooyoo').

3. BOOLEAN DATA TYPE
Boolean data types can have one of two values: true or false.


## RULES FOR NAMING VARIABLES

1. The name must begin with a letter, dollar sign ($),or an underscore (_). It must not start with a number.

2. The name can contain letters,numbers, dollar sign ($), or an underscore (_). Note that you must not use a dash(-) or a period (.) in a variable name.

3. You cannot use keywords or reserved words. Keywords are special words that tell the interpreter to dosomething. For example, var is a keyword used to declare a variable. Reservedwords are ones that may be used in a future version of JavaScript.

4. All variables are case sensitive, so score and Score would be different variable names, but it is bad practice to create two variables that have the same name using different cases.


5. Use a name that describes the kind of information that the variable stores. For example, fi rstName might be used to store a person's first name, l astNarne for their last name, and age for their age.



## ARRAYS

An array is a special type of variable. It doesn't just store one value; it stores a list of values.
Arrays are especially helpful when you do not know how many items a list will contain because, when you create the array, you do not need to specify how many values it will hold

## EXPRESSIONS

An expression evaluates into (results in) a single value. Broadly speaking there are two types of expressions.
1. EXPRESSIONS THAT JUST ASSIGN A VALUE TO A VARIABLE
2. EXPRESSIONS THAT USE TWO OR MORE VALUES TO RETURN A SINGLE VALUE


## OPERATORS

Expressions rely on things called operators; they allow programmers to create a single value from one or more values.

1. ARITHMETIC OPERATORS
JavaScript contains the following mathematical operators, which you can use with numbers. You may remember some from math class.

2. STRING OPERATOR 
There is just one string operator: the+ symbol. It is used to join the strings on either side of it
 MIXING NUMBERS AND STRINGS TOGETHER


## DECISIONS & loops

### if Statement

Use the if statement to specify a block of JavaScript code to be executed if a condition is true
if (condition) {
  //  block of code to be executed if the condition is true
}

  Use the else statement to specify a block of code to be executed if the condition is false

if (condition) {
  //  block of code to be executed if the condition is true
} else {
  //  block of code to be executed if the condition is false
}

 ### SWITCH STATEMENTS
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



## To Write a Git Commit Message Commit messages matte:
The seven rules of a great Git commit message Keep in mind:
 This has all been said before.
1. Separate subject from body with a blank line
2. Limit the subject line to 50 characters
3. Capitalize the subject line
4. Do not end the subject line with a period
5. Use the imperative mood in the subject line
6. Wrap the body at 72 characters
7. Use the body to explain what and why vs. how

 sources :

- Jon Duckett HTML & CSS Design and Build Websites ©2011 by John Wiley & Sons, Inc., Indianapolis, Indiana
- Jon Duckett JAVASCRIPT & JQUERY Interactive Front-End Web Development ©2014 by John Wiley & Sons, Inc., Indianapolis, Indiana
- https://chris.beams.io/posts/git-commit/
=======
- Jon Duckett HTML & CSS Design and Build Websites ©2011 by John Wiley & Sons, Inc., Indianapolis, Indiana
- Jon Duckett JAVASCRIPT & JQUERY Interactive Front-End Web Development ©2014 by John Wiley & Sons, Inc., Indianapolis, Indiana
- https://chris.beams.io/posts/git-commit/
 
>>>>>>> 19a557dc3537d06c9fb65a07f22bb773f32144d1
