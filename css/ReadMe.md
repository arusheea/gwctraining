# CSS Basic Guide 

Now we have learned how to make a web page using HTML, but it doesn't look so pretty. So we're going to dive into Cascading Style Sheets or CSS which is used to design web pages made in HTML.   

### Contents 

- [Introduction: What is CSS?](#intro)
- [Adding CSS to an HTML document](#adding)
- [Selectors](#selectors)
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
- **External style documents:** We can link an external CSS file by making a CSS file (a document with a .css extension) and linking it to our HTML document. This is especially useful if we want to use the same stylesheet for various HTML documents instead of rewriting it. We do so by using a `<link>` tag in the head of the document. It looks something like this: `<link href="style.css" rel="stylesheet">`.

## <a name="selectors"></a>Selectors

Selectors can have different levels of specificity:
- Tag names: 

## <a name="help"></a>Online Help and Resources

- [W3Schools](https://www.w3schools.com/css/default.asp) is a great website to learn more about CSS. It has examples of various things you might want to do with CSS, a list of selectors and properties and values, and interactive environments where you can easily play with CSS and see how it affects your page. 
- [CSS Diner](https://flukeout.github.io/) is a fun game created to help people practice using CSS selectors appropriately, with a mix of real and made up HTML tags.  

## <a name="exercises"></a>Exercises

- [Exercise 1](https://arusheea.github.io/gwctraining/css/exercises-solutions/exercise1.html)
- [Exercise 2](https://arusheea.github.io/gwctraining/css/exercises-solutions/exercise2.html)