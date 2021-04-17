# IMAGES

## controling the size of images in css

You can control the size of an image using the width and height properties in CSS, just
like you can for any other box. Specifying image sizes helps pages to load more smoothly
because the HTML and CSS code will often load before the images, and telling the browser
how much space to leave for an image allows it to render the rest of the page without
waiting for the image to download.

## AligNi ng images Using CSS

float property can be used to move an element to the left or the right of its containing block,
allowing text to flow around it. Rather than using the < mg> element's align attribute, web
page authors are increasingly using the float property to align images. There are two ways that
this is commonly achieved:

1. The float property is added to the class that was created to represent the size of the image

2. New classes are created with names such as align-left or align-right to align the images to the left or right of the page. These class names are used in addition to classes that indicate the size of the image.



## Centering images Using CSS

images are inline elements. This means that they flow within the surrounding text.
In order to center an image, itm should be turned into a blocklevel element using the display
property with a value of block. Once it has been made into a block-level element, there are
two common ways in which you can horizontally center an image:

1. On the containing element, you can use the text-align property with a value of center.

2. On the image itself, you can use the use the margin property and set the values of the left and right margins to auto.

## Background Images

*background-image* 

The background-image property allows you to place an image behind any HTML
element. This could be the entire page or just part of the page. By default, a background image will
repeat to fill the entire box. The path to the image follows the letters url, and it is put
inside parentheses and quotes. you can see a background image being applied to an entire page
(because the CSS selector applies to the < body> element). In the second example, the background image just applies to
a paragraph.



## epeating Images
*background-repeat*
*background-attachment*

The background-repeat property can have four values:

*repeat*
The background image is repeated both horizontally and vertically (the default way it
is shown if the backgroundrepeat property isn't used).

*repeat-x*
The image is repeated horizontally only.

*repeat-y*
The image is repeated vertically only.

*no-repeat*
The image is only shown once. The background-attachment property specifies whether a
background image should stay in one position or move as the user scrolls up and down the page.
It can have one of two values:

*fixed*
The background image stays in the same position on the page.

*scroll*
The background image moves up and down as the user scrolls up and down the page.



## Background Position

*background-position*

When an image is not being repeated, you can use the background-position
property to specify where in the browser window the background image should be placed.
This property usually has a pair of values. The first represents the horizontal position and the
second represents the vertical.

*left top*
*left center*
*left bottom*
*center top*
*center center*
*center bottom*
*right top*
*right center*
*right bottom*


## shorthand

*background*

The background property acts like a shorthand for all of the other background properties
you have just seen, and also the background-color property. The properties must be specified
in the following order, but you can miss any value if you do not want to specify it.

1. background-color
2. background-image
3. background-repeat
4. background-attachment
5. background-position

CSS3 will also support the use of multiple background images by repeating the background
shorthand. Because few browsers supported this property at the time of writing, it was not commonly used.



## Image Rollovers & Sprites

it is possible to create a link or button that changes to a second style when a user moves
their mouse over it (known as a rollover) and a third style when they click on it.
This is achieved by setting a background image for the link or button that has three different
styles of the same button (but only allows enough space to show one of them at a time).
You can see the image we are using in this example on the right. It actually features two
buttons on the one image. When the user moves their mouse over the element, or
clicks on it, the position of the background image is moved to show the relevant image.


CSS3: Gradients

*background-image*

CSS3 is going to introduce the ability to specify a gradient for the background of a box. The
gradient is created using the background-image property and, at the time of writing,
different browsers required a different syntax. Since it is not supported by all
browsers, it is possible to specify a background image for the box first (which would represent the
gradient) and then provide the CSS alternatives for browsers that support gradients.

## Contrast of background images

If you want to overlay text on a background image, the image must be low
contrast in order for the text to be legible.

1. High Contrast
The majority of photographs have quite a high contrast, which means that they are not ideal for
use as a background image.

2. Low Contrast 
Image editing applications such as Photoshop and GIMP have tools that allow you to manually
adjust your images to have lower contrast.

3. Screen
To overlay text on an image with high contrast, you can place a semi-transparent background color (or "screen") behind the
text to improve legibility.


# Practical Information

Search Engine Optimization (SEO )

* The Basics
Search engine optimization (or SEO) is the practice of trying to help your site appear nearer the top of search engine results when people look for the topics that your website covers. At the heart of SEO is the idea of
working out which terms people are likely to enter into a search engine to find your site and then
using these terms in the right places on your site to increase the chances that search engines will show a link to your site in their results.

* On-Page Techniques
On-page techniques are the methods you can use on your web pages to improve their
rating in search engines. The main component of this is looking at keywords that people 
are likely to enter into a search engine if they wanted to find your site, and then including 
these in the text and HTML code for your site in order to help the search engines know that your
site covers these topics. Search engines rely very heavily on the text that is in your pages
so it is important that the terms people are going to search for are in text. There are seven
essential places where you want your keywords to appear.

* Off-Page Techniques
Getting other sites to link to you is just as important as on-page techniques. Search engines help
determine how to rank your site by looking at the number of other sites that link to yours. They are particularly interested in sites whose content is related to yours. For example, if you were running a website that
sold fish bait, then a link from a hairdresser is not likely to beconsidered as relevant as one
from an angling community. Search engines also look at the words between the opening
< a> tag and closing < /a> tag in the link. If the text in the link contains keywords (rather than
just click here or your website address) it may be considered more relevant.


## On-Page SEO

In every page of your website there are seven key places where keywords
(the words people might search on to find your site) can appear in order
to improve its findability.

1. Page Title
The page title appears at the top of the browser window or on the tab of a browser. It is specified in
the < title> element which lives inside the <head> element.

2. URL / Web Address
The name of the file is part of the URL. Where possible, use keywords in the file name.

3. Headings
If the keywords are in a heading < hn> element then a searchengine will know that this page is
all about that subject and give it greater weight than other text.

4. Text
Where possible, it helps to repeat the keywords in the main body of the text at least 2-3
times. Do not, however, over-use these terms, because the text must be easy for a human to read.

5. Link Text
Use keywords in the text that create links between pages (rather than using generic expressions such as "click here").

6. Image Alt Text
Search engines rely on you providing accurate descriptions of images in the alt text. This
will also help your images show up in the results of image-based searches.

7. Page Descriptions
The description also lives inside the < head> element and is specified using a < meta> tag.
It should be a sentence that describes the content of the page. (These are not shown in
the browser window but they may be displayed in the results pages of search engines.)


## How to Identify Keywords and Phrases

Determining which keywords to use on your site can be one of the
hardest tasks when you start to think about SEO. Here are six steps that
will help you identify the right keywords and phrases for your site.

1. Brainstorm 
List down the words that someone might type into Google to find your site. Be sure to include the various topics, products or services your site is about. It often helps to ask other people what words they would use to find your site because people less familiar with a topic might use different terms than you. (In particular, they are less likely to use industry-specific jargon.)

2. Organize 
Group the keywords into separate lists for the different sections or categories of your
website. For example, if your website was a pet shop you might have different categories for different animals (such as dogs, cats and rabbits). On a large site you may break this up further into sub-categories (for example,
separate groups for different pet food brands).

3. Research
There are several tools that let you enter your keywords and then they will suggest additional
keywords you might like to consider, such as: adwords.google.co.uk/ select/KeywordToolExternal

4. Compare
It is very unlikely that your site will appear at the top of the search results for every
keyword. This is especially true for topics where there is a lot of competition. The more sites
out there that have already been optimized for a given keyword, the harder it will be for you to
rise up the search results when people search on that term.

5. Refine
Now you need to pick which keywords you will focus on. These should always be the ones
that are most relevant to each section of your site. If there is a phrase that is very
relevant but you find there is a lot of competition, you should still use it. To improve the
chances of your site being found you can look at whether there are other words that could be
incorporated into a phrase. For example, if the information or service you offer on your website
is location specific, then you will often find that incorporating your location into your keyword
list will help people find you.


6. Map
Now that you have a refined list of keywords, you know which have the most competition, and
which ones are most relevant, it is time to start picking which keywords you will use for each
page.



## Analytics: Learning about your Visitors

* Signing Up
The Google Analytics service relies on you signing up for an account at:
www.google.com/analytics The site will give you a piece of
tracking code which you need to put on every page of your site.

* How it Works
Every time someone loads a page of your site, the tracking code sends data to the Google
servers where it is stored. Google then provides a webbased
interface that allows you to see how visitors use your site.

* The Tracking Code
A tracking code is provided by Google Analytics for each website you are tracking. It
should appear just before the closing < /head> tag. The code does not alter the appearance of your web pages.


## How Many People Are Coming to Your Site?

The overview page gives you a snapshot of the key information you are
likely to want to know. In particular, it tells you how many people are
coming to your site.

*Visits*
This is the number of times people have come to your site. If someone is inactive on your site
for 30 minutes and then looks at another page on your site, it will be counted as a new visit.

*Unique Visits*
This is the total number of people who have visited your site
over the specified period. The number of unique visits will be lower than the number of visits
if people have been returning to your site more than once in the defined period.

*Page Views*
The total number of pages all visitors have viewed on your site. 

*Pages per Visit*
The average number of pages each visitor has looked at on your site per visit.

*Average Time on Site*
 he average amount of time each user has spent on the site per visit.

*Date Selector*
Using the date selector in the top right hand corner of the site, you can change the period of time
the reports display. When you log in, this is usually set to the last month, but you can change
it to report on a specific time period.

*Export*
The export link just above the title that says "visitors overview" allows you to export the
statistics on this page for other applications such as Excel.


FTP programs allow you to transfer files from your local computer to your web server.
Many companies provide platforms for blogging, email newsletters, e-commerce and other popular website
tools (to save you writing them from scratch).


## Audio and video elements
I think we've taught you enough in this article. The HTMLMediaElement API makes a wealth of functionality available for creating simple video and audio players, and that's only the tip of the iceberg. See the "See also" section below for links to more complex and interesting functionality.

Here are some suggestions for ways you could enhance the existing example we've built up:

The time display currently breaks if the video is an hour long or more (well, it won't display hours; just minutes and seconds). Can you figure out how to change the example to make it display hours?

Because < audio> elements have the same HTMLMediaElement functionality available to them, you could easily get this player to work for an < audio> element too. Try doing so.

Can you work out a way to turn the timer inner < div> element into a true seek bar/scrobbler — i.e., when you click somewhere on the bar, it jumps to that relative position in the video playback? As a hint, you can find out the X and Y values of the element's left/right and top/bottom sides via the getBoundingClientRect() method, and you can find the coordinates of a mouse click via the event object of the click event, called on the Document object. 

