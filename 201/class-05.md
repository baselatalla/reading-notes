# Images

## Choosing Images for Your Site
A picture can say a thousand words, and great images help make the difference
between an average-looking site and a really engaging one. where images should:

1. Be relevant
2. Convey information
3. Convey the right mood
4. Be instantly recognisable
5. Fit the color palette

## Storing Images on Your Site

storing images in a separate folder is a best practice which helps understand how the site is organized On a big site you might like to add subfolders inside the images folder.


### Adding Images

< img> images.html HTML To add an image into the page you need to use an < img>
element. This is an empty element (which means there is no closing tag). It must carry the
following two attributes:

1. src
This tells the browser where it can find the image file. This will usually be a relative URL
pointing to an image on your own site.

2. alt
This provides a text description of the image which describes them image if you cannot see it.

3. title
You can also use the title attribute with the < img> element to provide additional information
about the image. Most browsers will display the content of this attribute in a tootip when the
user hovers over the image.



### Height & Width of Images

You will also often see an < img> element use two other attributes that specify its size:
1. height
This specifies the height of the image in pixels.
2. width
This specifies the width of the image in pixels

### Where to Place Images in Your Code 

Where an image is placed in the code will affect how it is displayed. Here are three examples of image placement
that produce different results:

1. before a paragraph The paragraph starts on a new line after the image.
2. inside the start of a paragraphm The first row of text aligns with the bottom of the image.
3. in the middle of a paragraph The image is placed between the words of the paragraph that it appears in.


### Three Rules for Creating Images

1. Save images in the right format
Websites mainly use images in jpeg, gif, or png format. If you choose the wrong image format then your image might not look as sharp as it should and can make the web page slower to load.

2. save images at the right size
You should save the image at the same width and height it will appear on the website. If the image is smaller than the
width or height that you have specified, the image can be distorted and stretched. If the image is larger than the 
width and height if you have specified, the image will take longer to display on the page.

3. Use the correct resolution
Computer screens are made up of dots known as pixels. Images used on the web are also made
up of tiny dots. Resolution refers to the number of dots per inch, and most computer screens only
show web pages at 72 pixels per inch. So saving images at a higher resolution results in
images that are larger than necessary and take longer to download.

### Tools to Edit & Save Images

There are several tools you can use to edit and save images to ensure that they are the right size, format, and resolution.

* Softwares:
 - Adobe Photoshop
 - Adobe Fireworks
 - Pixelmator
 - PaintShop Pro
 - Paint.net

2. Software
 - Adobe Fireworks
 - Pixelmator
 - PaintShop Pro
 - Paint.net

#### Image Formats: JPEG
Whenever you have many different colors in a picture you should use a JPEG.
A photograph that features snow or an overcast sky might look like it has large areas that are just white or gray, but
the picture is usually made up of many different colors that are subtly different.

#### Image Formats: GIF
Use GIF or PNG format when saving images with few colors or large areas of the same color.



### Image Resolution

Images created for the web should be saved at a resolution of 72 ppi. The higher the resolution
of the image, the larger the size of the file.
JPGs, GIFs, and PNGs belong to a type of image format known as bitmap. They are made up of
lots of miniature squares. The resolution of an image is the number of squares that fit within
a 1 inch x 1 inch square area. Images appearing on computer screens are made of tiny squares called pixels.


### HTML 5: Figure and Figure Caption

* < figure>
Images often come with captions. HTML5 has introduced a new < figure> element to
contain images and their caption so that the two are associated. You can have more than one
image inside the < figure> element as long as they all share the same caption.

* < figcaption>
The < figcaption> element has been added to HTML5 in order to allow web page authors to add
a caption to an image. Before these elements were created there was no way to associate an <img> element with its 
caption.



# Color

## Foreground Color 

### color 
The color property allows you to specify the color of text inside an element. You can specify any color in CSS in one of three ways:
1. rgb values
These express colors in terms of how much red, green and blue are used to make it up. For example: rgb(100,100,90)

2. hex codes
These are six-digit codes that represent the amount of red, green and blue in a color, preceded by a pound or hash #
sign. For example: #ee3e80

3. color names 
There are 147 predefined color names that are recognized by browsers. For example: DarkCyan



### Background Color

*background-color*

CSS treats each HTML element as if it appears in a box, and the background-color property sets the color of the 
background for that box. You can specify your choice of background color in the same three ways you can specify
foreground colors: RGB values, hex codes, and color names


### Contrast

When picking foreground and background colors, it is important to ensure that there is enough contrast for the text to 
be legible.

1. A lack of contrast is particularly a problem for those with visual impairments and color blindness.
2. Text is easier to read when there is higher contrast between background and foreground colors.
3. For long spans of text, reducing the contrast a little bit improves readability.



 ### CSS 3: Opacity

*opacity, rgba*

CSS3 introduces the opacity property which allows you to specify the opacity of an element
and any of its child elements. The value is a number between 0.0 and 1.0 (so a value of 0.5 is 50%   
opacity and 0.15 is 15% opacity)
The CSS3 rgba property allows you to specify a color, just like you would with an RGB value, but adds a fourth value to
indicate opacity. This value is known as an alpha value and is number between 0.0 and 1.0


### CSS 3: HSL Colors

*hsl*, *hsla*

The hsl color property has been introduced in CSS3 as an alternative way to specify colors.
The value of the property starts with the letters hsl, followed  by individual values inside
parentheses for:

1. hue
This is expressed as an angle
(between 0 and 360 degrees).

2. saturation
This is expressed as a percentage.

3. lightness
This is expressed as a percentage with 0% being white, 50% being normal, and 100% being black.

4. alpha
This is expressed as a number between 0 and 1.0. For example, 0.5 represents 50% transparency, and 0.75
represents 75% transparency



# Text

### Specifying Typefaces

*font-family*

The font-family property allows you to specify the typeface that should be used for
any text inside the element(s) to which a CSS rule applies. The value of this property is the
name of the typeface you want to use.

### Size of Type

*font-size*

The font-size property enables you to specify a size for the font. There are several ways to
specify the size of a font. The most common are:

1. pixels
Pixels are commonly used because they allow web designers very precise control over how much space their text
takes up. The number of pixels is followed by the letters px.

2. percentages
The default size of text in browsers is 16px. So a size of 75% would be the equivalent of
12px, and 200% would be 32px.

3. ems
An em is equivalent to the width of a letter m.



![Screenshot_8](https://user-images.githubusercontent.com/55560502/110219172-50d9af80-7ec6-11eb-98ca-ef051e1c67d6.png)



### More Font Choice

*@font-face*

@font-face allows you to use a font, even if it is not installed on the computer of the personbrowsing, by allowing you to
specify a path to a copy of the font, which will be downloaded if it is not on the user's machine. Because this 
technique allows a version of the font to be downloaded to the user's computer, it is important that the
license for the font permits it to be used in this way.

*font-family*
This specifies the name of the font. This name can then be used as a value of the font-family
property in the rest of the style sheet (as shown in the rule for the < h1> and < h2> elements).


*src*
This specifies the path to the font. In order for this technique to work in all browsers, you will probably    
need to specify paths to a few different versions of the font, as shown on the next page

*format*
This specifies the format that the font is supplied in.




### Bold

*font-weight*

The font-weight property allows you to create bold text. There are two values that this
property commonly takes:

1. *normal*
This causes text to appear at a normal weight.

2. *bold*
This causes text to appear bold.



### Iticle

*font-style* 

If you want to create italic text, you can use the font-style property. There are three values
this property can take:

1. *normal*
This causes text to appear in a normal style (as opposed to italic or oblique).

2. *italic* 
This causes text to appear italic. oblique This causes text to appear oboblique.



### UpperCase & LowerCase 

*text-transform*

The text-transform property is used to change the case of text giving it one of the following values:

1. *uppercase* 
This causes the text to appear uppercase.

2. *lowercase*
This causes the text to appear lowercase.

3. *capitalize*
This causes the first letter of each word to appear capitalized.


### Underline & Strike

*text-decoration*

The text-decoration property allows you to specify the following values:

1. *none*
This removes any decoration already applied to the text.

2. *underline*
This adds a line underneath the text.

3. *overline*
This adds a line over the top of the text.

4. *line-through*
This adds a line through words. blink This animates the text to make it flash on and off (however this is
generally frowned upon, as it is considered rather annoying).

### Leading

*line-height*

Leading (pronounced ledding) is a term typographers use for the vertical space between lines of
text. In a typeface, the part of a letter that drops beneath the baseline is called a descender,
while the highest point of a letter is called the ascender. Leading is measured from the bottom of
the descender on one line to the top of the ascender on the next.

### Letter & Word Spacing

*letter-spacing*
 *word-spacing*

 Kerning is the term
typographers use for the space between each letter. You can control the space between each
letter with the letter-spacing property. It is particularly helpful to increase the kerning when
your heading or sentence is all in uppercase. If your text is in sentence (or normal) case,
increasing or decreasing the kerning can make it harder to read.

### Alignment

*text-align*

The text-align property allows you to control the alignment of text. The property can take one
of four values:

1. *left*
This indicates that the text should be left-aligned.

2. *right*
This indicates that the text should be right-aligned.

3. *center*
This allows you to center text.

4. *justify*
This indicates that every line in a paragraph, except the last line, should be set to take up the full
width of the containing box.



### Vertical Alignment

*vertical-align*

The vertical-align property is a common source of confusion. It is not intended to allow you to
vertically align text in the middle of block level elements such as < p> and < div>, although it does
have this effect when used with table cells (the < td> and < th> elements). It is more commonly used with
inline elements such as < img>, < em>, or <strong> elements. When used with these elements,
it performs a task very similar to the HTML align attribute used on the <img> element, which
you met on pages 103-106. The values it can take are:

*baseline*
*sub*
*super*
*top*
*text-top*
*middle*
*bottom*
*text-bottom*


### Indenting Text

*text-indent*

The text-indent property allows you to indent the first line of text within an element.
The amount you want the line indented by can be specified in a number of ways but is usually given in pixels or ems.
It can take a negative value, which means it can be used to push text off the browser
window. You can see this technique used in this example, where the < h1> element uses a background image to represent
the heading. The text has been moved far to the left, off the screen.


### CSS3: Drop Shadow

*text-shadow*

The text-shadow property has become commonly used despite lacking support in all browsers.
It is used to create a drop shadow, which is a dark version of the word just behind it and
slightly offset. It can also be used to create an embossed effect by adding a shadow that is slightly
lighter than the text. The value of this property is quite complicated because it can
take three lengths and a color for the drop shadow.


### First Lett er or Line

*:first-letter* 
*:first-line*

You can specify different values for the first letter or first line of text inside an element using
:first-letter and :first-line. Technically these are not properties. They are known as
pseudo-elements. You specify the pseudo-element at the end of the selector, and then specify the declarations as
you would normally for any other element.


### Styling Links

*:link* 
*:visited*

Browsers tend to show links in blue with an underline by default, and they will change
the color of links that have been visited to help users know which
pages they have been to. In CSS, there are two pseudoclasses that allow you to set different styles for links that
have and have not yet been visited.

1. *:link*
This allows you to set styles for links that have not yet been visited.


2. *:visited*
This allows you to set styles for links that have been clicked on. They are commonly used to
control colors of the links and also whether they are to appear underlined or not.



### Responding to Users

*:hover*, *:active*, *:focus*

There are three pseudo-classes that allow you to change the appearance of elements when a
user is interacting with them.

1. *:hover*
This is applied when a user hovers over an element with a pointing device such as a mouse.
This has commonly been used to change the appearance of links and buttons when a user
places their cursor over them. It is worth noting that such events do not work on devices that use 
touch screens (such as the iPad) because the screen is not able to tell when someone is hovering
their finger over an element.

2. *:active*
This is applied when an element is being activated by a user; for example, when a button is being
pressed or a link being clicked. Sometimes this is used to make a button or link feel more like it
is being pressed by changing the style or position of the element slightly.

3. *:focus*
This is applied when an element has focus. Any element that you can interact with, such as a
link you can click on or any form control can have focus.



### Attribute Selectors



![Screenshot_9](https://user-images.githubusercontent.com/55560502/110219178-5cc57180-7ec6-11eb-8c53-fde637ae7517.png)
