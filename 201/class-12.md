
# CHART.JS

Charts are far better for displaying data visually than tables and have the added benefit that no one is ever going to press-gang them into use as a layout tool. They’re easier to look at and convey data quickly, but they’re not always easy to create.

### Setting up

 The first thing we need to do is download Chart.js. Copy the Chart.min.js out of the unzipped folder and into the directory you’ll be working in. Then create a new html page and import the script.
 
 
![Screenshot_1](https://user-images.githubusercontent.com/55560502/111086141-4b621200-8523-11eb-879c-bf55de362a13.png)


### Drawing a line chart

To draw a line chart, the first thing we need to do is create a canvas element in our HTML in which Chart.js can draw our chart. So add this to the body of our HTML page:


![Screenshot_2](https://user-images.githubusercontent.com/55560502/111086167-6896e080-8523-11eb-8699-c79916c69fbf.png)


Next, we need to write a script that will retrieve the context of the canvas, so add this to the foot of your body element:



![Screenshot_3](https://user-images.githubusercontent.com/55560502/111086178-72204880-8523-11eb-8625-ea177f3fc761.png)

Inside the same script tags we need to create our data, in this instance it’s an object that contains labels for the base of our chart and datasets to describe the values on the chart. Add this immediately above the line that begins ‘var buyers=’:


![Screenshot_4](https://user-images.githubusercontent.com/55560502/111086181-78162980-8523-11eb-9ab0-c5f8daf990c9.png)


### Drawing a pie chart

Our line chart is complete, so let’s move on to our pie chart. First, we need the canvas element:


![Screenshot_5](https://user-images.githubusercontent.com/55560502/111086188-806e6480-8523-11eb-88e4-44821266d57d.png)

Next, we need to get the context and to instantiate the chart:


![Screenshot_6](https://user-images.githubusercontent.com/55560502/111086195-882e0900-8523-11eb-89f5-4ecd972fc51d.png)


You’ll notice that this time, we are going to supply some options to the chart. Next we need to create the data. This data is a little different to the line chart because the pie chart is simpler, we just need to supply a value and a color for each section:


![Screenshot_7](https://user-images.githubusercontent.com/55560502/111086199-8d8b5380-8523-11eb-800a-68dd9b5171d9.png)

Now, immediately after the pieData we’ll add our options:

![Screenshot_8](https://user-images.githubusercontent.com/55560502/111086203-92500780-8523-11eb-8b8d-2d68e624f018.png)


### Drawing a bar chart

Finally, let’s add  a bar chart to our page. Happily the syntax for the bar chart is very similar to the line chart we’ve already added. First, we add the canvas element:


![Screenshot_13](https://user-images.githubusercontent.com/55560502/111086298-012d6080-8524-11eb-8825-6c0a6cbea3a4.png)



Next, we retrieve the element and create the graph:



![Screenshot_12](https://user-images.githubusercontent.com/55560502/111086264-dcd18400-8523-11eb-867c-7c5ecdc20d4f.png)


And finally, we add in the bar chart’s data:

![Screenshot_10](https://user-images.githubusercontent.com/55560502/111086215-9ed46000-8523-11eb-878d-3dfcc46d63c1.png)

## Chart.js docs

### Installation

You can download the latest version of Chart.js from the GitHub releases or use a Chart.js CDN. Detailed installation instructions can be found on the installation page.

### Creating a Chart

It's easy to get started with Chart.js. All that's required is the script included in your page along with a single <canvas> node to render the chart.

In this example, we create a bar chart for a single dataset and render that in our page. You can see all the ways to use Chart.js in the usage documentation.


![Screenshot_11](https://user-images.githubusercontent.com/55560502/111086309-11ddd680-8524-11eb-8b19-ca90f3f5c871.png)


### Contributing

Before submitting an issue or a pull request to the project, please take a moment to look over the contributing guidelines first.

For support using Chart.js, please post questions with the chartjs tag on Stack Overflow.

### License

Chart.js is available under the MIT license.

# Basic usage of canvas

## The < canvas> element

At first sight a < canvas> looks like the < img> element, with the only clear difference being that it doesn't have the src and alt attributes. Indeed, the < canvas> element has only two attributes, width and height. These are both optional and can also be set using DOM properties. When no width and height attributes are specified, the canvas will initially be 300 pixels wide and 150 pixels high. The element can be sized arbitrarily by CSS, but during rendering the image is scaled to fit its layout size: if the CSS sizing doesn't respect the ratio of the initial canvas, it will appear distorted.

The id attribute isn't specific to the < canvas> element but is one of the global HTML attributes which can be applied to any HTML element (like class for instance). It is always a good idea to supply an id because this makes it much easier to identify it in a script

## Fallback content

The < canvas> element differs from an < img> tag in that, like for < video>, < audio>, or < picture> elements, it is easy to define some fallback content, to be displayed in older browsers not supporting it, like versions of Internet Explorer earlier than version 9 or textual browsers. You should always provide fallback content to be displayed by those browsers.

Providing fallback content is very straightforward: just insert the alternate content inside the < canvas> element. Browsers that don't support < canvas> will ignore the container and render the fallback content inside it. Browsers that do support < canvas> will ignore the content inside the container, and just render the canvas normally.

## The rendering context

The < canvas> element creates a fixed-size drawing surface that exposes one or more rendering contexts, which are used to create and manipulate the content shown. In this tutorial, we focus on the 2D rendering context. Other contexts may provide different types of rendering

## Checking for support
The fallback content is displayed in browsers which do not support < canvas>. Scripts can also check for support programmatically by testing for the presence of the getContext() method.




# Drawing shapes with canvas 

## The grid

Before we can start drawing, we need to talk about the canvas grid or coordinate space. Our HTML skeleton from the previous page had a canvas element 150 pixels wide and 150 pixels high. To the right, you see this canvas with the default grid overlayed. Normally 1 unit in the grid corresponds to 1 pixel on the canvas. The origin of this grid is positioned in the top left corner at coordinate (0,0). All elements are placed relative to this origin. So the position of the top left corner of the blue square becomes x pixels from the left and y pixels from the top, at coordinate (x,y). Later in this tutorial we'll see how we can translate the origin to a different position, rotate the grid and even scale it, but for now we'll stick to the default.

## Drawing rectangles

Unlike SVG, < canvas> only supports two primitive shapes: rectangles and paths (lists of points connected by lines). All other shapes must be created by combining one or more paths. Luckily, we have an assortment of path drawing functions which make it possible to compose very complex shapes.

## Drawing paths


Now let's look at paths. A path is a list of points, connected by segments of lines that can be of different shapes, curved or not, of different width and of different color. A path, or even a subpath, can be closed. To make shapes using paths, we take some extra steps:

1. First, you create the path.
2. Then you use drawing commands to draw into the path.
3. Once the path has been created, you can stroke or fill the path to render it.

## Moving the pen

One very useful function, which doesn't actually draw anything but becomes part of the path list described above, is the moveTo() function. You can probably best think of this as lifting a pen or pencil from one spot on a piece of paper and placing it on the next.


## Lines
For drawing straight lines, use the lineTo() method. lineTo(x, y)
Draws a line from the current drawing position to the position specified by x and y.
This method takes two arguments, x and y, which are the coordinates of the line's end point. The starting point is dependent on previously drawn paths, where the end point of the previous path is the starting point for the following, etc. The starting point can also be changed by using the moveTo() method.




## Applying styles and colors

Colors
Up until now we have only seen methods of the drawing context. If we want to apply colors to a shape, there are two important properties we can use: fillStyle and strokeStyle.

color is a string representing a CSS < color>, a gradient object, or a pattern object. We'll look at gradient and pattern objects later. By default, the stroke and fill color are set to black (CSS color value #000000).



## Transparency

In addition to drawing opaque shapes to the canvas, we can also draw semi-transparent (or translucent) shapes. This is done by either setting the globalAlpha property or by assigning a semi-transparent color to the stroke and/or fill style.

globalAlpha = transparencyValue
Applies the specified transparency value to all future shapes drawn on the canvas. The value must be between 0.0 (fully transparent) to 1.0 (fully opaque). This value is 1.0 (fully opaque) by default.
The globalAlpha property can be useful if you want to draw a lot of shapes on the canvas with similar transparency, but otherwise it's generally more useful to set the transparency on individual shapes when setting their colors.




## Drawing text


Drawing text
The canvas rendering context provides two methods to render text:

fillText(text, x, y [, maxWidth])
Fills a given text at the given (x,y) position. Optionally with a maximum width to draw.
strokeText(text, x, y [, maxWidth])
Strokes a given text at the given (x,y) position. Optionally with a maximum width to draw.

## Styling text

In the examples above we are already making use of the font property to make the text a bit larger than the default size. There are some more properties which let you adjust the way the text gets displayed on the canvas:

font = value
The current text style being used when drawing text. This string uses the same syntax as the CSS font property. The default font is 10px sans-serif.
textAlign = value
Text alignment setting. Possible values: start, end, left, right or center. The default value is start.
textBaseline = value
Baseline alignment setting. Possible values: top, hanging, middle, alphabetic, ideographic, bottom. The default value is alphabetic.
direction = value
Directionality. Possible values: ltr, rtl, inherit. The default value is inherit.
These properties might be familiar to you, if you have worked with CSS before.

## Advanced text measurements

In the case you need to obtain more details about the text, the following method allows you to measure it.

measureText()
Returns a TextMetrics object containing the width, in pixels, that the specified text will be when drawn in the current text style.

## Gecko-specific notes
In Gecko (the rendering engine of Firefox, Firefox OS and other Mozilla based applications), some prefixed APIs were implemented in earlier versions to draw text on a canvas. These are now deprecated and removed, and are no longer guaranteed to work.

