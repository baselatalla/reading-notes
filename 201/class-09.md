# Forms

Traditionally, the term 'form' has referred to a printed document that contains
spaces for you to fill in information. HTML borrows the concept of a form to refer to different
elements that allow you to collect information from visitors to your site.

In addition to enabling users to search, forms also allow users to perform other functions online. You will see forms
when registering as a member of a website, when shopping online, and when signing up for
newsletters or mailing lists.

## Form Controls

There are several types of form controls that you can use to collect information from visitors to your site:

1. ADDING TEXT:

* Text input (single-line)
Used for a single line of text such as email addresses and names.

* Password input
Like a single line text box but it masks the characters entered.

* Text area (multi-line)
For longer areas of text, such as messages and comments.


2. Making Choices:

* Radio buttons
For use when a user must select one of a number of options.

* Checkboxes
When a user can select and unselect one or more options.

* Drop-down boxes
When a user must pick one of a number of options from a list.


3. Submitting Forms:

* Submit buttons
To submit data from your form to another web page.

* Image buttons
Similar to submit buttons but they allow you to use an image.

4. Uploadi ng Files:

* File upload
Allows users to upload files (e.g. images) to a website.



## How Forms Work 


1. A user fills in a form and then presses a button to submit the information to the server. 

2. The name of each form control is sent to the server along with the value the user enters or selects.

3. The server processes the information using a programming language such as PHP, C#, VB.net, or Java. It may also store the information in a database. 

4. The server creates a new page to send back to the browser based on the information received.


A form may have several form controls, each gathering different information. The server needs to
know which piece of inputted data corresponds with which form element.

To differentiate between various pieces of inputted data, information is sent from the browser 
to the server using name/value pairs.

If the form control allows the user to enter text, then the value of the form control is whatever 
the user has typed in.

If the form control allows you to choose from a fixed set of answers (e.g. radio buttons, checkboxes 
or a drop down list), the web page author will add code that gives each option an automatic value.


## Form Structure

*< form>*
Form controls live inside a < form> element. This element should always carry the action
attribute and will usually have a method and id attribute too.

*action*
Every < form> element requires an action attribute. Its value is the URL for the page on the
server that will receive the information in the form when it is submitted

*method*
Forms can be sent using one of two methods: _get_ or _post_.

**get**
With the get method, the values from the form are added to the end of the URL specified 
in the action attribute. The get method is ideal for:

● short forms (such as search boxes)

● when you are just retrieving data from the web server (not sending information that
should be added to or deleted from a database)

**post**
With the post method the values are sent in what are known as HTTP headers. As a
rule of thumb you should use the post method if your form:

● allows users to upload a file.

● is very long.

● contains sensitive data (e.g. passwords)

● adds information to, or deletes information from, a database


## Tex t Input

*< input>*
The < input> element is used to create several different form controls. The value of the type
attribute determines what kind of input they will be creating.

*type="text"*
When the type attribute has a value of text, it creates a singleline text input.

*name*
When users enter information into a form, the server needs to know which form control each
piece of data was entered into. (For example, in a login form, the server needs to know what has
been entered as the username and what has been given as the password.) Therefore, each form
control requires a name attribute. The value of this attribute identifies the form control and is
sent along with the information they enter to the server.

*maxlength*
You can use the maxlength attribute to limit the number of characters a user may enter
into the text field. Its value is the number of characters they may enter. For example, if you were
asking for a year, the maxlength attribute could have a value of 4.


## Password Input 

*< input>*

*type="password"*
When the type attribute has a value of password it creates a text box that acts just like a
single-line text input, except the characters are blocked out. They are hidden in this way so
that if someone is looking over the user's shoulder, they cannot see sensitive data such as
passwords.

*name*
The name attribute indicates the name of the password input, which is sent to the server with
the password the user enters. size, maxlength It can also carry the size and
maxlength attributes like the the single-line text input


## TEXT AREA 

*< textarea>*
The < textarea> element is used to create a mutli-line text input. Unlike other input
elements this is not an empty element. It should therefore have an opening and a closing tag.
Any text that appears between the opening < textarea> and closing < /textarea> tags will
appear in the text box when the page loads.

If the user does not delete any text between these tags, this message will get sent to the
server along with whatever the user has typed. (Some sites use JavaScript to clear this
information when the user clicks in the text area.)

## Radio Button

*< input>*

*type="radio"*
Radio buttons allow users to pick just one of a number of options.

*name*
The name attribute is sent to the server with the value of the option the user selects. When
a question provides users with options for answers in the form of radio buttons, the value of
the name attribute should be the same for all of the radio buttons used to answer that question.

*value*
The value attribute indicates the value that is sent to the server for the selected option.
The value of each of the buttons in a group should be different (so that the server knows which
option the user has selected).

*checked*
The checked attribute can be used to indicate which value (if any) should be selected when
the page loads. The value of this attribute is checked. Only one radio button in a group should
use this attribute.


## Checkbox

*< input>*

*type="checkbox"*
Checkboxes allow users to select (and unselect) one or more options in answer to a question.

*name*
The name attribute is sent to the server with the value of the option(s) the user selects. When
a question provides users with options for answers in the form of checkboxes, the value of the
name attribute should be the same for all of the buttons that answer that question.

*value*
The value attribute indicates the value sent to the server if this checkbox is checked.
checked The checked attribute indicates that this box should be checked when the page loads. If used



## Drop Down Li st Box 

*< select>*
A drop down list box (also known as a select box) allows users to select one option from a
drop down list. The < select> element is used to create a drop down list box. It
contains two or more < option> elements.

*name*
The name attribute indicates the name of the form control being sent to the server, along with the
value the user selected.

*< option>*
The < option> element is used to specify the options that the user can select from. The words
between the opening < option> and closing < /option> tags will be shown to the user in the drop
down box.'

*value*
The < option> element uses the value attribute to indicate the value that is sent to the server
along with the name of the control if this option is selected.

*selected*
The selected attribute can be used to indicate the option that should be selected when the
page loads. The value of this attribute should be selected


## Multiple Se lec t Box

*< select>*

*size*
You can turn a drop down select box into a box that shows more than one option by adding the
size attribute. Its value should be the number of options you want to show at once. In the
example you can see that three of the four options are shown. Unfortunately, the way that
browsers have implemented this attribute is not perfect, and it should be tested throroughly if
used (in particular in Firefox and Safari on a Mac). multiple You can allow users to select
multiple options from this list by adding the multiple attribute with a value of multiple.


## File Input Box

<input>
If you want to allow users to upload a file (for example an image, video, mp3, or a PDF), you
 will need to use a file input box.

*type="file"*
This type of input creates a box that looks like a text input followed by a browse button.
When the user clicks on the browse button, a window opens up that allows them to select a
file from their computer to be uploaded to the website.

## Submit Button

*< input>*

*type="submit"*
The submit button is used to send a form to the server.

*name*
It can use a name attribute but it does not need to have one.

*value*
The value attribute is used to control the text that appears on a button. It is a good idea to
specify the words you want to appear on a button because the default value of buttons on some
browsers is ‘Submit query’ and this might not be appropriate for all kinds of form.


## Image Button 

*< input>*

*type="image"*
If you want to use an image for the submit button, you can give the type attribute a value of
image. The src, width, height, and alt attributes work just like they do when used with the
*< img>* element


## Button & hidden Controls

*< button>*
The <button> element was introduced to allow users more control over how their buttons
appear, and to allow other elements to appear inside the button. This means that you can
combine text and images between the opening < button>
tag and closing < /button> tag.

*< input>*

*type="hidden"*
This example also shows a hidden form control. These form controls are not shown on the
page (although you can see them if you use the View Source option in the browser). They allow web
page authors to add values to forms that users cannot see. For example, a web page author
might use a hidden field to indicate which page the user was on when they submitted a form.


## La belling Form Controls

*< label>*
When introducing form controls, the code was kept simple by indicating the purpose of each
one in text next to it. However, each form control should have its own < label> element as this
makes the form accessible to vision-impaired users.

The < label> element can be used in two ways. It can:

1. Wrap around both the text description and the form input (as shown on the first line of the                          example to your right).

2. Be kept separate from the form control and use the for attribute to indicate which form control                      it is a label for (as shownwith the radio buttons).

*for*
The for attribute states which form control the label belongs to. Note how the radio buttons use
the id attribute. The value of the id attribute uniquely identifies an element from all other elements
on a page.


## Grouping Form Elements

*< fieldset>*
You can group related form controls together inside the < fieldset> element. This is
particularly helpful for longer forms.Most browsers will show the fieldset with a line
around the edge to show how they are related. The appearance of these lines can be adjusted using CSS.

*< legend>*
The < legend> element can come directly after the opening < fieldset> tag and contains acaption 
which helps identify the purpose of that group of form controls.


## HTML 5: Form Validation

Traditionally, form validation has been performed using JavaScript (which is beyond the
scope of this book). But HTML5 is introducing validation and leaving the work to the browser.
Validation helps ensure the user enters information in a form that the server will be able to  
understand when the form is submitted. Validating the contents of the form before it is sent to 
the server the helps:

● Reduce the amount of work the server has to do.

● Enables users to see if there are problems with the form faster than if validation were
performed on the server.

## HTML 5: Date Input 

*< input>*
Many forms need to gather information such as dates, email addresses, and URLs. This has
traditionally been done using text inputs. HTML5 introduces new form controls to standardize the
way that some information is gathered. Older browsers that do not recognize these inputs
will just treat them as a single line text box.

*type="date"*
If you are asking the user for a date, you can use an < input>
element and give the type attribute a value of date. This will create a date input in
browsers that support the new HMTL5 input types.


## HTML 5: Email & URL Input

*< input>*
HTML5 has also introduced inputs that allow visitors to enter email addresses and URLs.
Browsers that do not support these input types will just treat them as text boxes.

*type="email"*
If you ask a user for an email address, you can use the email input. Browsers that support
HTML5 validation will check that the user has provided information in the correct format
of an email address. Some smart phones also optimize their keyboard to display the keys you
are most likely to need when entering an email address (such as the @ symbol).

*type="url"*
A URL input can be used when you are asking a user for a web page address. Browsers that
support HTML5 validation will check that the user has provided information in the format of
a URL. Some smart phones also optimize their keyboard to display the keys you are most
likely to need when entering a URL.

HTML 5: Search Input

*< input>*
If you want to create a single line text box for search queries, HTML5 provides a special type
of input for that purpose.

*type="search"*
If you want to create a single line text box for search queries, HTML5 provides a special
search input. To create the HTML5 search box the <input> element should
have a type attribute whose value is search. Older browsers will simply treat it like a single
line text box.

Recent browsers add some features that improve usability. For example, Safari on a Mac
adds a cross to clear the search box when you have started to enter information. Safari also
automatically rounds the corners on the search input field.

*placeholder*
On any text input, you can also use an attribute called placeholder whose value is
text that will be shown in the text box until the user clicks in that area. Older browsers simply
ignore this attribute



# Lists, Tables and Forms

In addition to the CSS properties covered in other chapters which work with the contents of all elements,
there are several others that are specifically used to control the appearance of lists, tables, and forms.

List markers can be given different appearances using the list-style-type and list-style image
properties.

Table cells can have different borders and spacing in different browsers, but there are properties you can
use to control them and make them more consistent.

Forms are easier to use if the form controls are vertically aligned using CSS.Forms benefit from styles 
that make them feel more
interactive.



# EVENTS

## DIFFERENT EVENT TYPES

Here is a selection of the events that occur in the browser while you are
browsing the web. Any of these events can be used to trigger a function
in your JavaScript code.


![Screenshot_6](https://user-images.githubusercontent.com/55560502/110523157-66dfae00-811a-11eb-80c8-57a29f0360fd.png)


## TERMINOLOGY

* EVENTS FIRE OR ARE RAISED
When an event has occurred, it is often described as having fired or
been raised. In the diagram on the right, if the user is tapping on a link, a
cl ick event would fire in the browser.

* EVENTS TRIGGER SCRIPTS
Events are said to t rigger a function or script. When the click event
fires on the element in this diagram, it could trigger a script that enlarges
the selected item.


![Screenshot_7](https://user-images.githubusercontent.com/55560502/110523182-6f37e900-811a-11eb-8492-026c84d76cd5.png)



## HOW EVENTS TRIGGER JAVASCRIPT CODE

When the user interacts with the HTML on a web page, there are three
steps involved in getting it to trigger some JavaScript code.
Together these steps are known as event handling.

1. Select t he element node(s) you want the script to respond to.
2. Indicate which event on the selected node(s) will trigger the response.                                                Programmers call this binding an event to a DOM node.
3. State the code you want to run when the event occurs. When the event occurs,                                         on a specified element, it will triggera function. This may be a named or an anonymous function.



Here you can see how event handling can be used to provide feedback to
users filling in a registration form. It will show an error message if their
username is too short.

1. SELECT ELEMENT 
The element that users are interacting with is the text input where they enter the username.

2. SPEC!FY EVENT 
When users move out of the text input, it loses focus, and the blur event fires on this element.

3. CALL CODE
When the blur event fires on the username input, it will trigger a function called
chec kUsername ().This function checks if the username is less than 5 characters.


Binding is the process of stating which event you are waiting to happen, and which element you are waiting
for that event to happen upon. When an event occurs on an element, it can trigger a JavaScript function. When this function then changes the web page in some way, it feels interactive because it has responded to the user.
You can use event delegation to monitor for events that happen on all of the children of an element.
The most commonly used events are W3C DOM events, although there are others in the HTMLS
specification as well as browser-specific events.
