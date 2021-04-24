# Regex

Regular expressions (regex or regexp) are extremely useful in extracting information from any text by searching for 
one or more matches of a specific search pattern for a specific sequence of ASCII or unicode characters.Fields of 
application range from validation to parsing/replacing strings, passing through translating data to other formats 
and web scraping.


You use this tool in (almost) all programming languages ​​(JavaScript, Java, VB, C #, C / C++, Python, Perl, Ruby, Delphi, R, Tcl, and many others) with the slightest distinctions about the support of the most advanced features and syntax versions supported by the engines.


## Basic topics

#### Anchors : ^ and $

1. ^The    :      matches any string that starts with _*The*_.
2. end$    :      matches a string that ends with *_end_*.
3. ^The end$  :   exact string match (starts and ends with _*The end*_)
4. roar    :      matches any string that has the text roar in it.


#### Quantifiers : _* + ? and {}_

1. abc*     :     matches a string that has ab followed by zero or more c. 
2. abc+     :     matches a string that has ab followed by one or more c.
3. abc?     :     matches a string that has ab followed by zero or one c.
4. abc{2}   :     matches a string that has ab followed by 2 c.
5. c{2,}    :     matches a string that has ab followed by 2 or more c.
6. c{2,5}   :     matches a string that has ab followed by 2 up to 5 c.
7. bc)*     :     matches a string that has a followed by zero or more copies of the sequence bc.
8. bc){2,5} :     matches a string that has a followed by 2 up to 5 copies of the sequence bc.


#### OR operator :  _| or []_

1. a(b|c)     matches a string that has a followed by b or c (and captures b or c).
2. a[bc]      same as previous, but without capturing b or c.

#### Character classes :  _\d \w \s and ._

1. \d         matches a single character that is a digit.
2. \w         matches a word character (alphanumeric character plus underscore).
3. \s         matches a whitespace character (includes tabs and line breaks).
4. _._          matches any character.


Use the . operator carefully since often class or negated character class (which we’ll cover next)
are faster and more precise.
\d, \w and \s also present their negations with \D, \W and \S respectively.
For example, \D will perform the inverse match with respect to that obtained with \d.

5. \D    :     matches a single non-digit character.

In order to be taken literally, you must escape the characters ^.[$()|*+?{\with a backslash \ as they have special meaning.

6. \$\d       matches a string that has a $ before one digit.


*Notice* that you can match also non-printable characters like tabs \t, new-lines \n, carriage returns \r.

### Flags
We are learning how to construct a regex but forgetting a fundamental concept: flags.
A regex usually comes within this form /abc/, where the search pattern is delimited by two slash characters /. At the end we can specify a flag with these values (we can also combine them each other):
g (global) does not return after the first match, restarting the subsequent searches from the end of the previous match
m (multi-line) when enabled ^ and $ will match the start and end of a line, instead of the whole string
i (insensitive) makes the whole expression case-insensitive (for instance /aBc/i would match AbC)


### Intermediate topics

#### Grouping and capturing   :  ()

1. a(bc)        :   parentheses create a capturing group with value bc.
2. a(?:bc)*     :   using ?: we disable the capturing group.
3. a(?<foo>bc)  :   using ?<foo> we put a name to the group.


This operator is very useful when we need to extract information from strings or data using your preferred programming language. Any multiple occurrences captured by several groups will be exposed in the form of a classical array: we will access their values specifying using an index on the result of the match.
If we choose to put a name to the groups (using (?<foo>...)) we will be able to retrieve the group values using the match result like a dictionary where the keys will be the name of each group.


#### Bracket expressions  :  []

[abc]            matches a string that has either an a or a b or a c -> is the same as a|b|c.
[a-c]            same as previous.
[a-fA-F0-9]      a string that represents a single hexadecimal digit, case insensitively.
[0-9]%           a string that has a character from 0 to 9 before a % sign
[^a-zA-Z]        a string that has not a letter from a to z or from A to Z. In this case the ^ is used as negation of the expression.


### Greedy and Lazy match

The quantifiers ( * + {}) are greedy operators, so they expand the match as far as they can through the provided text. For example, <.+> matches <div>simple div</div> in This is a <div> simple div</div> test. In order to catch only the div tag we can use a ? to make it lazy:

<.+?>      :      matches any character one or more times included inside < and >, expanding as needed.
Notice that a better solution should avoid the usage of . in favor of a more strict regex:
<[^<>]+>   :      matches any character except < or > one or more times included inside < and >\ .



### Advanced topics


#### Boundaries  :  \b and \B

1. \babc\b       :     performs a "whole words only" search 

\b represents an anchor like caret (it is similar to $ and ^) matching positions where one side is a word character (like \w) and the other side is not a word character (for instance it may be the beginning of the string or a space character). It comes with its negation, \B. This matches all positions where \b doesn’t match and could be if we want to find a search pattern fully surrounded by word characters.

2. \Babc\B     :     matches only if the pattern is fully surrounded by word characters.


#### Back-references :  \1

1. ([abc])\1             :   using \1 it matches the same text that was matched by the first capturing group.
2. ([abc])([de])\2\1     :   we can use \2 (\3, \4, etc.) to identify the same text that was matched 
                         :   by the second (third, fourth, etc.) capturing group.
3. (?<foo>[abc])\k<foo>  :   we put the name foo to the group and we reference it later (\k<foo>).
                         :   The result is the same of the first regex.


#### Look-ahead and Look-behind  :  (?=) and (?<=)

1. d(?=r)     :   matches a d only if is followed by r, but r will not be part of the overall regex match.
2. (?<=r)d    :   matches a d only if is preceded by an r, but r will not be part of the overall regex match.
           :   You can use also the negation operator!
3. d(?!r)     :   matches a d only if is not followed by r, but r will not be part of the overall regex match.
4. (?<!r)d    :   matches a d only if is not preceded by an r, but r will not be part of the overall regex match.







# CSS Grid Layout

(aka “Grid”), is a two-dimensional grid-based layout system that aims to do nothing less than completely change the way we design grid-based user interfaces. CSS has always been used to lay out our web pages, but it’s never done a very good job of it. First, we used tables, then floats, positioning and inline-block, but all of these methods were essentially hacks and left out a lot of important functionality (vertical centering, for instance). Flexbox helped out, but it’s intended for simpler one-dimensional layouts, not complex two-dimensional ones (Flexbox and Grid actually work very well together). Grid is the very first CSS module created specifically to solve the layout problems we’ve all been hacking our way around for as long as we’ve been making websites.



## Important terminology

1. Grid Container
The element on which display: grid is applied. It’s the direct parent of all the grid items. In this example container is the grid container.

2. The children (i.e. direct descendants) of the grid container. Here the item elements are grid items, but sub-item isn’t. 

3. Grid Line
The dividing lines that make up the structure of the grid. They can be either vertical (“column grid lines”) or horizontal (“row grid lines”) and reside on either side of a row or column. Here the yellow line is an example of a column grid line.


4. Grid Cell
The space between two adjacent row and two adjacent column grid lines. It’s a single “unit” of the grid. Here’s the grid cell between row grid lines 1 and 2, and column grid lines 2 and 3.

5. Grid Track
The space between two adjacent grid lines. You can think of them like the columns or rows of the grid. Here’s the grid track between the second and third row grid lines.

6. Grid Area
The total space surrounded by four grid lines. A grid area may be composed of any number of grid cells. Here’s the grid area between row grid lines 1 and 3, and column grid lines 1 and 3.



## Grid properties

### Properties for the Parent (Grid Container)

1. display :

Defines the element as a grid container and establishes a new grid formatting context for its contents.

Values:

- grid – generates a block-level grid
- inline-grid – generates an inline-level grid

2. grid-template-columns & grid-template-rows

Defines the columns and rows of the grid with a space-separated list of values. The values represent the track size, and the space between them represents the grid line.

Values:

- track-size – can be a length, a percentage, or a fraction of the free space in the grid (using the fr unit)
- line-name – an arbitrary name of your choosing

3. grid-template-areas

Defines a grid template by referencing the names of the grid areas which are specified with the grid-area property. Repeating the name of a grid area causes the content to span those cells. A period signifies an empty cell. The syntax itself provides a visualization of the structure of the grid.

Values:

- grid-area-name – the name of a grid area specified with grid-area
- . – a period signifies an empty grid cell
- none – no grid areas are defined

That’ll create a grid that’s four columns wide by three rows tall. The entire top row will be composed of the header area. The middle row will be composed of two main areas, one empty cell, and one sidebar area. The last row is all footer.


4. grid-template

A shorthand for setting grid-template-rows, grid-template-columns, and grid-template-areas in a single declaration.

Values:

- none – sets all three properties to their initial values
- grid-template-rows / grid-template-columns – sets grid-template-columns and grid-template-rows to the specified values, respectively, and sets grid-template-areas to none.

Since grid-template doesn’t reset the implicit grid properties (grid-auto-columns, grid-auto-rows, and grid-auto-flow), which is probably what you want to do in most cases, it’s recommended to use the grid property instead of grid-template.

5. column-gap & row-gap & grid-column-gap & grid-row-gap


Specifies the size of the grid lines. You can think of it like setting the width of the gutters between the columns/rows.

Values:

- line-size – a length value.


6. gap & grid-gap

A shorthand for row-gap and column-gap

Values:

- grid-row-gap / grid-column-gap – length values

If no row-gap is specified, it’s set to the same value as column-gap.

7. justify-items

Aligns grid items along the inline (row) axis (as opposed to align-items which aligns along the block (column) axis). This value applies to all grid items inside the container.

Values:

- start – aligns items to be flush with the start edge of their cell
- end – aligns items to be flush with the end edge of their cell
- center – aligns items in the center of their cell
- stretch – fills the whole width of the cell (this is the default)

8. align-items

Aligns grid items along the block (column) axis (as opposed to justify-items which aligns along the inline (row) axis). This value applies to all grid items inside the container.

Values:

- start – aligns items to be flush with the start edge of their cell
- end – aligns items to be flush with the end edge of their cell
- center – aligns items in the center of their cell
- stretch – fills the whole height of the cell (this is the default)

9. place-items

place-items sets both the align-items and justify-items properties in a single declaration.

Values:

- align-items / justify-items – The first value sets align-items, the second value justify-items. If the second value is omitted, the first value is assigned to both properties.


10. justify-content

Sometimes the total size of your grid might be less than the size of its grid container. This could happen if all of your grid items are sized with non-flexible units like px. In this case you can set the alignment of the grid within the grid container. This property aligns the grid along the inline (row) axis (as opposed to align-content which aligns the grid along the block (column) axis).

Values:

- start – aligns the grid to be flush with the start edge of the grid container
- end – aligns the grid to be flush with the end edge of the grid container
- center – aligns the grid in the center of the grid container
- stretch – resizes the grid items to allow the grid to fill the full width of the grid container
- space-around - places an even amount of space between each grid item, with half-sized spaces on the far ends
- space-between – places an even amount of space between each grid item, with no space at the far ends
- space-evenly – places an even amount of space between each grid item, including the far ends

11. align-content

Sometimes the total size of your grid might be less than the size of its grid container. This could happen if all of your grid items are sized with non-flexible units like px. In this case you can set the alignment of the grid within the grid container. This property aligns the grid along the block (column) axis (as opposed to justify-content which aligns the grid along the inline (row) axis).

Values:

- start – aligns the grid to be flush with the start edge of the grid container
- end – aligns the grid to be flush with the end edge of the grid container
- center – aligns the grid in the center of the grid container
- stretch – resizes the grid items to allow the grid to fill the full height of the grid container
- space-around – places an even amount of space between each grid item, with half-sized spaces on the far ends
- space-between – places an even amount of space between each grid item, with no space at the far ends
- space-evenly – places an even amount of space between each grid item, including the far ends



### Properties for the Children (Grid Items)

1. grid-column-start & grid-column-end & grid-row-start & grid-row-end

Determines a grid item’s location within the grid by referring to specific grid lines. grid-column-start/grid-row-start is the line where the item begins, and grid-column-end/grid-row-end is the line where the item ends.

Values:

- line – can be a number to refer to a numbered grid line, or a name to refer to a named grid line
- span number - the item will span across the provided number of grid tracks
- span name – the item will span across until it hits the next line with the provided name
- auto – indicates auto-placement, an automatic span, or a default span of one.

2. grid-column & grid-row

Shorthand for grid-column-start + grid-column-end, and grid-row-start + grid-row-end, respectively.

Values:

- start-line / end-line – each one accepts all the same values as the longhand version, including span

3. grid-area

Gives an item a name so that it can be referenced by a template created with the grid-template-areas property. Alternatively, this property can be used as an even shorter shorthand for grid-row-start + grid-column-start + grid-row-end + grid-column-end.

Values:

- name – a name of your choosing
- row-start / column-start / row-end / column-end – can be numbers or named lines.


4. justify-self

Aligns a grid item inside a cell along the inline (row) axis (as opposed to align-self which aligns along the block (column) axis). This value applies to a grid item inside a single cell.

Values:

- start – aligns the grid item to be flush with the start edge of the cell
- end – aligns the grid item to be flush with the end edge of the cell
- center – aligns the grid item in the center of the cell
- stretch – fills the whole width of the cell (this is the default)

5. align-self

Aligns a grid item inside a cell along the block (column) axis (as opposed to justify-self which aligns along the inline (row) axis). This value applies to the content inside a single grid item.

Values:

- start – aligns the grid item to be flush with the start edge of the cell
- end – aligns the grid item to be flush with the end edge of the cell
- center – aligns the grid item in the center of the cell
- stretch – fills the whole height of the cell (this is the default)

6. place-self

place-self sets both the align-self and justify-self properties in a single declaration.

Values:

- auto – The “default” alignment for the layout mode.
- align-self / justify-self – The first value sets align-self, the second value justify-self. If the second value 
- is omitted, the first value is assigned to both properties.
