# CSS Basic Guide 

Now we have learned how to make a web page using HTML, but it doesn't look so pretty. So we're going to dive into Cascading Style Sheets or CSS which is used to design web pages made in HTML.   

### Contents 

- [Introduction: What is CSS?](#intro)
- [Adding CSS to an HTML document](#adding)
- [Basic Selectors](#selectors)
- [What can we style?](#whatwedo)
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

- `width` and `height`: specify the width and height of an element with a unit (pixels px, cm, mm, etc.) or as a percentage of the containing element.
- `max-width` and `max-height`: specify the maximum width and height of the element. This is useful if the height and width are dependent on the page size, and we want to ensure it doesn't get larger than a certain size.
- `min-width` and `min-height`: specify the minimum width and height of the element. This is useful if the height and width are dependent on the page size, and we want to ensure it doesn't get smaller than a certain size. 

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

- margin: the outer space around an element is specified here, with some unit (pixels px, cm, mm, etc.). For e.g. in `helloworld.html`, the div elements all are of width 500 pixels, and have a 15 pixel margin on all four sides, which separates them from the sides of the page and from each other. 
- padding: the inner space within the element is specified here, with some unit (pixels px, cm, mm, etc.). For e.g. n `helloworld.html`, the div elements all are of width 500 pixels, and have a 15 pixel padding on all four sides, which separates the content from the border of the div. 

> We can specify margin/padding in several ways:
> - a single value, which will give the same margin/padding in all directions. 
> - two space-separated values, out of which the first will be used for the top and bottom, and second for the right and left. 
> - four space-separated values, which will be considered in the order: top, right, bottom, left.
> - we can also use specific directional properties, i.e. margin-right, margin-top, padding-right, padding-bottom, etc. 

- background-color: used to specify a background color 
- color: specifies the color of text within the styled element

> Note on CSS color values: Color can be specified using either 
> - The 140 [predefined colors in HTML](https://www.w3schools.com/colors/colors_names.asp)
> - Functions that generate colors, for e.g. rgb(red-value, green-value, blue-value)/rgba(red-value, green-value, blue-value, transparency) where the first the color values must be between 0 and 255, and the transparency is between 0 and 1
> - Hex values, of the format #(3 or 6 digit code)

- display: changes the default display value of elements to block, inline, inline-block, and none (removes the element from the document). Block and Inline were discussed in the HTML module, but inline-block is different in that it stays on the same line like inline elements but respects width, height, padding and margin properties provided (which inline elements do not).

## <a name="help"></a>Online Help and Resources

- [W3Schools](https://www.w3schools.com/css/default.asp) is a great website to learn more about CSS. It has examples of various things you might want to do with CSS, a list of selectors and properties and values, and interactive environments where you can easily play with CSS and see how it affects your page. 
- [CSS Diner](https://flukeout.github.io/) is a fun game created to help people practice using CSS selectors appropriately, with a mix of real and made up HTML tags.  

## <a name="exercises"></a>Exercises

- [Exercise 1](https://arusheea.github.io/gwctraining/css/exercises-solutions/exercise1.html)
- [Exercise 2](https://arusheea.github.io/gwctraining/css/exercises-solutions/exercise2.html)