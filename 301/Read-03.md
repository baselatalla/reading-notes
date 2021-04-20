# Javascript Templating Language and Engine— Mustache.js with Node and Express

## Javascript Templating

Javascript templating is a fast and efficient technique to render client-side view templates with Javascript by using a JSON data source. The template is HTML markup, with added templating tags that will either insert variables or run programming logic.

The template engine then replaces variables and instances declared in a template file with actual values at runtime, and convert the template into an HTML file sent to the client.
Mustache


Mustache is a logic-less template syntax. It can be used for HTML, config files, source code — anything. It works by expanding tags in a template using values provided in a hash or object.

## Mustache-Express
If you intend you use mustache with Node and Express, you can use mustache-express. Mustache Express lets you use Mustache and Express together easily. To install:

With Yarn:
$ yarn add mustache-express

or with NPM:
$ npm install mustache --save

Configure mustache-express in your server.js/app.js/index.js file:
11111111

Create a views folder and add some html view templates (e.g. hello.html):
2222222
3333333

Then in the router configuration, use res.render(TEMPLATE_NAME, JSON_DATA). Example:

res.render('hello', {"name": "Sherlynn"})

Whereby the first parameter ‘hello’ refers to the hello.html file (no need to include the extension (e.g. hello.html) as it has been previously set as html.
The second parameter would be the JSON data itself. We can also pass in a variable representing the data, for example:

var nameObject = {"name": "Sherlynn"}

res.render('hello', nameObject)



Final output:

4444


# A Complete Guide to Flexbox


## Background
The Flexbox Layout (Flexible Box) module (a W3C Candidate Recommendation as of October 2017) aims at providing a more efficient way to lay out, align and distribute space among items in a container, even when their size is unknown and/or dynamic (thus the word “flex”).

The main idea behind the flex layout is to give the container the ability to alter its items’ width/height (and order) to best fill the available space (mostly to accommodate to all kind of display devices and screen sizes). A flex container expands items to fill available free space or shrinks them to prevent overflow.


## Basics and terminology

Since flexbox is a whole module and not a single property, it involves a lot of things including its whole set of properties. Some of them are meant to be set on the container (parent element, known as “flex container”) whereas the others are meant to be set on the children (said “flex items”).

If “regular” layout is based on both block and inline flow directions, the flex layout is based on “flex-flow directions”. Please have a look at this figure from the specification, explaining the main idea behind the flex layout.

5555

## Flexbox properties

### Properties for the Parent (flex container)

1. display
This defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.

2. order
By default, flex items are laid out in the source order. However, the order property controls the order in which they appear in the flex container.

3. flex-direction
the four possible values of flex-direction being shown: top to bottom, bottom to top, right to left, and left to right

This establishes the main-axis, thus defining the direction flex items are placed in the flex container. Flexbox is (aside from optional wrapping) a single-direction layout concept. Think of flex items as primarily laying out either in horizontal rows or vertical columns.

4. flex-grow
This defines the ability for a flex item to grow if necessary. It accepts a unitless value that serves as a proportion. It dictates what amount of the available space inside the flex container the item should take up.

5. flex-wrap
By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property.

6. flex-shrink
This defines the ability for a flex item to shrink if necessary.

7. flex-basisThis defines the default size of an element before the remaining space is distributed. It can be a length (e.g. 20%, 5rem, etc.) or a keyword. The auto keyword means “look at my width or height property” (which was temporarily done by the main-size keyword until deprecated)


8. flex-flow
This is a shorthand for the flex-direction and flex-wrap properties, which together define the flex container’s main and cross axes. The default value is row nowrap.

9. justify-content
This defines the alignment along the main axis. It helps distribute extra free space leftover when either all the flex items on a line are inflexible, or are flexible but have reached their maximum size. It also exerts some control over the alignment of items when they overflow the line.

10. align-self
This allows the default alignment (or the one specified by align-items) to be overridden for individual flex items.
Please see the align-items explanation to understand the available values.

11. align-items
This defines the default behavior for how flex items are laid out along the cross axis on the current line. Think of it as the justify-content version for the cross-axis (perpendicular to the main-axis).

## Prefixing Flexbox

Flexbox requires some vendor prefixing to support the most browsers possible. It doesn’t just include prepending properties with the vendor prefix, but there are actually entirely different property and value names. This is because the Flexbox spec has changed over time, creating an “old”, “tweener”, and “new” versions.