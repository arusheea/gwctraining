# CSS Basic Guide 

Now we have learned how to make a web page using HTML, but it doesn't look so pretty. So we're going to dive into Cascading Style Sheets or CSS which is used to design web pages made in HTML.   

### Contents 

- [Introduction: What is CSS?](#intro)
- [Adding CSS to an HTML document](#adding)
- [Basic Selectors](#selectors)
- [What can we style?](#whatwedo)
- [Some Examples](#examples)
- [Advanced Selectors](#adv-select)
- [Online Help and Resources](#help)
- [Exercises](#exercises)

## <a name="intro"></a>Introduction: What is CSS?

- CSS is short for Cascading Style Sheets.
- It is a language used to describe the styles of different HTML elements in a document. 
- Unlike HTML, CSS has little to do with the content of a page, and primarily handles how that content is displayed, designed, and styled. Some examples of the things you can do with CSS include:
	- Change background colors of the page, and of objects within the page
	- Specify sizes and positions of images in your page 
	- Create fixed navigation bars 
	- Style tables to appear more user friendly 
- In CSS, we use selectors to specify which elements we are styling, and then provide details on what styles we want to apply, like this: 
	```
	<selector> {
		<property>: <value>;
	}
	```
- **Important Note:** Although CSS can dramatically change the way a page looks, it is important to write good HTML as well. Try to use appropriate tags for everything in HTML and then style according to your needs, for e.g. although we can style any word to look like a heading using CSS, we should always try to make headings using the `<h1>`...`<h6>` tags. 

## <a name="adding"></a>Adding CSS to an HTML document

There are three ways to add CSS to our HTML documents: 
- **Inline CSS:** We can add CSS styling for each individual element by adding it as an attribute in the HTML tag. This is useful if we have style to add to only one element in the page, but it is relatively inefficient if we have the same styles applied across various elements, because then if we need to change anything, we will have to go to each element and change it manually. An example of this is `<a href="example.com" style="text-decoration: none; color: red;">Click me</a>` This would create a red colored link saying 'Click me' that is not underlined. 
- **Style tags inside the document:** We can add CSS styles for the entire document between `<style>` tags inside the head. This is better than Inline CSS, because if we want to apply the same style across elements on the page, we can easily change it in one place to affect the whole document! An example of this can be seen in `helloworld.html`. (Don't worry about understanding what's within the style tags just yet, we will get into that soon!)
- **External style documents:** We can link an external CSS file by making a CSS file (a document with a .css extension) and linking it to our HTML document. This is especially useful if we want to use the same stylesheet for various HTML documents instead of rewriting it. We do so by using a `<link>` tag in the head of the document. It looks something like this: `<link href="style.css" rel="stylesheet">`. This tends to be my preferred way of adding CSS because 
	- We separate style from content.
	- More often than not, we have more than one web page in a website, and we want to keep the styling consistent for the website, and applying the same stylesheet to all pages is an easy way to do that. 

## <a name="selectors"></a>Basic Selectors

Selectors can have different levels of specificity. We need to use selectors to tell our CSS which elements we are styling, unless we use Inline CSS, because with inline, we are only specifying styles for a single element. Take a look at `helloworld.html` for examples mentioned in the sub-points, and see how they affect the page [here](https://arusheea.github.io/gwctraining/css/helloworld.html):
- **Tag names:** If we use a tag name as a selector, we apply the specified styles to all elements of that tag type across the page. For e.g. in `helloworld.html`, there is a `div` used as a selector. This means that all div tags on the page will have the specified styles, i.e. a solid red border, a width of 500 pixels, and an inner padding and outer margin of 15 pixels. 
- **Class names:** Classes can be applied to multiple elements, even of different types, so we can use those to collectively style some elements. For e.g. in `helloworld.html` we use the class "selector" to style all the selector names differently. We wrap "tag name", "id", "classes", etc. in `<span>` tags with the class as "selector" and then use that in our CSS by using a '.' (period) followed by the class name. 
- **Id names:** If you recall from the HTML module, id has to be unique in HTML, so each id can be used only once. So if we want to style one specific object differently, we can use the id selector by putting a '#' (pound sign) followed by the id. For e.g. in `helloworld.html`, we use the id "different-box" to specially style our third div tag. 

We will discuss more about selectors, and cover different ways of choosing specific elements in a page later on, but I'm sure you can already tell how important it is to consider selectors carefully while styling a document because it can save you so much tedium. 

## <a name="whatwedo"></a>What can we style?

Below we will discuss some common CSS properties, and the kinds of values they can take. 

### Sizing and spacing of elements 

- `width` and `height`: Specify the width and height of an element with a unit (pixels px, cm, mm, etc.) or as a percentage of the containing element.
- `max-width` and `max-height`: Specify the maximum width and height of the element. This is useful if the height and width are dependent on the page size, and we want to ensure it doesn't get larger than a certain size.
- `min-width` and `min-height`: Specify the minimum width and height of the element. This is useful if the height and width are dependent on the page size, and we want to ensure it doesn't get smaller than a certain size. 

> Absolute length units include:
> - cm (centimeters)
> - mm (millimeters)
> - in (inches)
> - px (pixels) - These are relative to the device the page is viewed on. 
> - pt (points)
> - pc (picas)
>
> Relative length units include: 
> - em - Relative to the font-size of the element's current font size. 
> - ch - Relative to width of the '0'.
> - rem - Relative to font-size of the root element.
> - vw (viewport width) - This is a percentage of the view window's width at any given point.
> - vh (viewport height) - This is a percentage of the view window's height at any given point.
> - vmin (viewport smallest dimension) - This is a percentage of the view window's smaller dimension at any given point.
> - vmax (viewport largest dimension) - This is a percentage of the view window's larger dimension at any given point.
> - % (percentage) - This is relative to the parent elements dimensions.

- `margin`: This is the outer space around an element is specified here, with some unit (pixels px, cm, mm, etc.). For e.g. in `helloworld.html`, the div elements all are of width 500 pixels, and have a 15 pixel margin on all four sides, which separates them from the sides of the page and from each other. 
- `padding`: This is the inner space within the element is specified here, with some unit (pixels px, cm, mm, etc.). For e.g. n `helloworld.html`, the div elements all are of width 500 pixels, and have a 15 pixel padding on all four sides, which separates the content from the border of the div. 

> We can specify margin/padding in several ways:
> - a single value, which will give the same margin/padding in all directions. 
> - two space-separated values, out of which the first will be used for the top and bottom, and second for the right and left. 
> - four space-separated values, which will be considered in the order: top, right, bottom, left.
> - we can also use specific directional properties, i.e. margin-right, margin-top, padding-right, padding-bottom, etc. 

- `box-sizing`: This is an important and interesting property. Its default value is content-box, which means that the width and height of an element do not include the borders and padding. The other value is border-box, which makes width and height include borders and padding. When we set box-sizing to border-box, the width and height are treated as the fixed values of width and height regardless of padding and borders. To understand this better, notice how the third div in `helloworld.html` is different from the others in terms of size. 

### Background formatting, borders, and colors 

> Note on CSS color values: Color can be specified using either 
> - The 140 [predefined colors in HTML](https://www.w3schools.com/colors/colors_names.asp)
> - Functions that generate colors, for e.g. rgb(red-value, green-value, blue-value)/rgba(red-value, green-value, blue-value, transparency) where the first the color values must be between 0 and 255, and the transparency is between 0 and 1
> - Hex values, of the format #(3 or 6 digit code)

- `color`: Specifies the color of text within the styled element.
- `opacity`: Takes a value between 0 and 1 as the opacity of the element. 0 is transparent, and 1 is opaque. 

**Background:**
- `background-color`: Used to specify a background color.
- `background-image`: A path to a local file or a link to an online image like this `url(path/link)` to set it as the background image of the specified element.
- `background-position`: Aligns the background image within the element to either any combination (left top, right center, center top etc.), two percentages as the distance of the left and bottom edges respectively from the top left corner of the container, or two values as the horizontal and vertical distance from the top left corner of the container respectively. 
- `background-size`: auto (original size) | length (two values that set the width and height) | percentage (two values that set the width and height as a percentage of the parent element) | cover (resize to fill the whole area) | contain (resize to have the full image fit in the area)
- `background-repeat`: repeat (repeat image in any direction if the background is too small) | repeat-x (repeat in only the horizontal direction) | repeat-y (repeat in only the vertical direction) | no-repeat (do not repeat) | space (repeat as much as possible without clipping) | round (repeat and squish/stretch the image to fill the whole area)
- `background`: Can be used to specify numerous properties of an element's background mentioned above, and a few more that are used as often. We can list numerous properties, space-separated, and they will all be applied to the background like the individual properties above are. Syntax is: `bg-color bg-image bg-position/bg-size bg-repeat ...` in any order.

**Borders:**
- `border-width`: Specifies the width of a border with some unit. There are also specific properties for the left, right, bottom and top border's width.
- `border-color`: Specifies the color of the border. There are also specific properties for the left, right, bottom and top border's color.
- `border-style`: Specifies the type of border (none, hidden, solid, dotted, dashed, double etc.) There are also specific properties for the left, right, bottom and top border's style.
- `border`: Like background, border can be used to specify several properties that can also be specified separately, however I usually prefer using the border tag to specify everything, like this: `border-width border-style border-color` in any order. The only case where this is not as useful is when we need variable border widths on different sides. 
- `border-radius`: This defines the curve radius of the element's corners. We can provide oen value (applied on all corners), two values (first for top-left, bottom-right and second for top-right, bottom-left), three values (first for top-left, second for top-right, bottom-left, and third for bottom-right), and four values (for top-left, top-right, bottom-right, bottom-left respectively). There are also specific properties for the top-left, top-right, bottom-left and bottom-right border radii. 
- `border-collapse`: This is primarily useful for tables because once we put a border value for tables, and their lines actually show up, they are double lines usually. Border collapse makes these double lines coverge into single lines for clean tables. The value just has to be set to 'collapse'. 

### Display properties and positioning 

- `display`: Changes the default display value of elements to block, inline, inline-block, and none (removes the element from the document). Block and Inline were discussed in the HTML module, but inline-block is different in that it stays on the same line like inline elements but respects width, height, padding and margin properties provided (which inline elements do not).
- `text-align`: Controls the alignment of text within an container, can be center, left, right etc. 
- `text-indent`: Controls how much the text in the given styled element will be indented from its aligned side. 
- `vertical-align`: Sets the vertical alignment of an element with respect to it's parent container. It's values can be baseline (default), length (amount to raise/lower from baseline), % (to raise/lower from baseline), sub (aligned with subscript baseline), super (aligned with superscript baseline), top (aligned to top of tallest element), text-top (aligned with top of font), middle (middle of parent element), bottom (aligned with lowest element), or text-bottom.
- `position`: Specifies an element's positioning method. 
	- static: default value, in document flow
	- absolute: element is positioned relevant to the first positioned (non-static) element
	- fixed: positioned relative to browser window (use left, right, top, bottom properties to move element around the page!)
	- relative: element positioned relative to it's default static position 
- `float`: Non-absolute positioned elements can float. Float is none by default but we can specify left or right to make elements move to the right or left by default. 
- `z-index`: This property is a number that specifies the arrangement of elements in the front or back of the page. The higher the z-index of an element, the higher up it will stack. So if two elements overlap at all, the one with a higher z-index will be at the top. 

### Text formatting

- `font-family`: Specifies the font family we wish to use in a given element. We can also write serif, sans-serif, or monospace to get the default fonts in each category. 
- `font-size`: Specifies the size of the text in the element.
- `font-style`: Allows us to make text italic or oblique, or just normal. 
- `font-weight`: Specifies the boldness/heaviness of the text in the element being styled, granted that the font family chosen has bolder or lighter options.
- `letter-spacing`: Specifies size of the whiespace between characters.
- `line-height`: Specifies the height of any line of text in the given styled element. 
- `font`: Allows us to specify all the font properties in one go, like we can with background and border. The syntax is: `font-size/line-height font-family font-style font-weight` in any order.
- `word-spacing`: Specifies size of the whitespace between words. 
- `text-decoration`: Allows us to specify the type(s) of text-decoration we want (underline, overline, or line-through), the color of the text-decoration, and the style (solid, wavy, dotted, dashed etc.) like so: `text-decoration-line text-decoration-color text-decoration-style` in any order. All three of these are also individual properties. Only the first value (line) is required out of the three. 

## <a name="examples"></a>Some Examples 

- Check out `navbar.html` and `navbar.css` for an example webpage with a navigation bar stuck to the top of a page. You can see it live [here](https://arusheea.github.io/gwctraining/css/navbar.html). 

## <a name="adv-select"></a>Advanced Selectors

More material will be added here soon! 

## <a name="help"></a>Online Help and Resources

- [W3Schools](https://www.w3schools.com/css/default.asp) is a great website to learn more about CSS. It has examples of various things you might want to do with CSS, a list of selectors and properties and values, and interactive environments where you can easily play with CSS and see how it affects your page. 
- [CSS Diner](https://flukeout.github.io/) is a fun game created to help people practice using CSS selectors appropriately, with a mix of real and made up HTML tags. 
- [Box Shadow Generator](https://www.cssmatic.com/box-shadow) is useful to automatically generate box shadows of your choice, which is easier usually than writing them from scratch. 
- [Text Shadow Generator](https://css3gen.com/text-shadow/) is useful in a similar way for making text shadows instead of writing them from scratch. 
- [Animation using CSS](https://www.w3schools.com/css/css3_animations.asp) is a rather complex topic, but if you're motivated and would like to try it after mastering the basics, then I recommend this resource. 

## <a name="exercises"></a>Exercises

- Exercise 1: You have been provided [this](https://arusheea.github.io/gwctraining/css/exercises/exercise1.html) page, called exercise1.html inside the exercises directory, and you have to make it look like [this](https://arusheea.github.io/gwctraining/css/exercises-solutions/exercise1.html) by adding CSS. 
- Exercise 2: You have been provided [this](https://arusheea.github.io/gwctraining/css/exercises/exercise2.html) page, called exercise2.html inside the exercises directory, and you have to make it look like [this](https://arusheea.github.io/gwctraining/css/exercises-solutions/exercise2.html) by adding CSS. 
- Suggested Challenge: Select a simple website you like, and pick a page (perhaps the homepage), and try to recreate it's content. You don't need to worry about interactivity just yet, but try to make it as close to the real thing as possible. It will motivate you to google and learn how to do various things that you might otherwise not try out. 