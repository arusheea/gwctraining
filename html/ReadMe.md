# HTML Basic Guide 

HTML is the first step to building a web page. In this module, you will get a basic introduction to what HTML is and see some samples HTML web pages. 

### Contents 

- [Introduction: What is HTML?](#intro)
- [Basics of an HTML page](#minimum)
	- [What is an HTML tag?](#tags)
	- [What is the head tag?](#head-tag)
	- [What is the body tag?](#body-tag)
	- [What are tag attributes?](#tag-attr)
	- [What comes next?](#next-step)
- [Formatting in HTML](#format)
	- [Text Formatting](#text-format)
- [Online Help and Resources](#help)

## <a name="intro"></a>Introduction: What is HTML?

- HTML is short for Hyper Text Markup Language. This means, HTML is used to define our web page's markup, or in simpler terms, to define content formatting. 
- HTML has had several versions in the past, and the most recent one is HTML5. 
- It's primary purpose is to define and label all the content on a web page. HTML can tell us what the title of a page should be, what our headings and subheadings are, what sections and links our page contains. 
- *It is important to note that HTML is **not** meant to alter the way our page looks*, i.e. it is not used for design purposes. For design, we will be using [CSS or Cascading Style Sheets](), which will be introduced in the next module.

## <a name="minimum"></a>Basics of an HTML page 

Refer to the following code or look at `helloworld.html` in this directory. We will now walk through the very basic requirements of an HTML page, and load it on a browser. 

```
<!DOCTYPE html>
<html>
  <head>
  	<meta charset='UTF-8'>
    <meta name="author" content="Your Name">
  	<title>My First HTML Page</title>
  </head>
  <body>
  	Hello World
  </body>
</html>
```

#### <a name="tags"></a>What is an HTML tag? 

- An HTML tag or element is an item within angular brackets, for e.g. `<html>`, `<head>`, etc. 
- HTML tags are often in pairs, with **an opening tag and a closing tag**. Closing tags are usually the same as the opening tag, but with a / after the &lt; and before the tag name. In the provided code, you can see that `<html>` has the closing tag `</html>`. 
- HTML Tags or elements are used to **define content elements** on the page. 
- For tags that have closing elements, the opening and closing tag define the content within them. For e.g. in the provided code, everything between the `<html>` and `</html>` tags is known to be html code. Further, everything between the `<head>` and `</head>` tags is called the body, and so on. 
- There are additionally some tags that do not have closing elements. These are usually used to define single elements, or properties of the page. In the provided code, `<meta>` and `<br>` are such **self-closing elements**. 
- Self closing tags are sometimes written with a `/` at the end, like so: `<br>` would be written as `<br />` Both are valid. This point was just to avoid confusion when reading code samples written elsewhere. 

##### NOTE:

- The first line `<!DOCTYPE>` is not a tag, but rather defines the type of the document. It tells the browser the version of html we are using, defaulting to the latest version. It is always declared at the top of the page, before the `<html>` tag.
- The `<html>` tag defines what is within our HTML document, so any information about the page or any content inside the page. 
- To make comments on html pages, include the comment between `<!--` and `-->`. Comments will not be visible to users looking at your web page, but they are useful for your own documentation. 

#### <a name="head-tag"></a>What is the head tag? 

- A head tag `<head>` is used to specify information about our web page, instead of the content. 
- None of the content inside the `<head>` tag is rendered on the web page/screen. 
- Several kinds of information come under this tag, including: 
	- The title of the page inside `<title>` tag indicates the title of the page that shows up at the top of the browser window. For e.g. in the provided code, the title of the page is 'My First HTML Page'. 
	- Any stylesheets (CSS files) we have connected to this web page or style information (inside `<style>` tags), or any scripts (JavaScript, Python, etc.) we are linking to this web page or scripts within the page (inside `<script>` tags), to add interactivity.
	- Meta-data about the page, like who the author is, what character sets we will be using, etc. as shown using the `<meta>` tag. [More on this here](https://www.w3schools.com/tags/tag_meta.asp).

#### <a name="body-tag"></a>What is the body tag?

- The body tag `<body>` is used to specify the body of the page, which has the actual contents of the page, including text, images, videos, hyperlinks, etc. 
- For e.g. in the example code, the body contains the text "Hello World" so if you load the web page, the only thing we see on the screen are these two words. If we change these two words, the content on the screen will change as well. 

#### <a name="tag-attr"></a>What are tag attributes?

Tag attributes are additional details provided for tags. An example of an attribute in the provided code would be `charset` for the `<meta>` tag. Some other examples include: 
- Anchor `<a>` tags are used to create hyperlinks. An important attribute for anchor tags is `href` which specifies where the hyperlink leads. So `<a href="example.com">click me</a>` would create a hyperlink leading to example.com. 
- Input `<input>` tags are used to create some kind of input in a form. An attribute we often need for input is `type` which specifies if we want a text box input, a checkbox, radio button, button, etc. 

Most html elements can be provided a `name`, `class`, or `id` attribute (or any combination thereof). These specifiers are useful in selecting/refering to elements or sets of elements when we write CSS for styling our web pages, or JavaScript to build interactivity. 
	- `name` just specifies a name for an element. For e.g. in the provided code, the name for the second meta tag is author, so we know there is a piece of meta data called author, with the content "Your Name".
	- `class` is used to create groups of elements in html pages, so several elements on the page can have the same class. These are used for several reasons, for example if we want to apply certain styling to some elements on the page, we can give them the same class name and write CSS for that class. 
	- `id` is a **unique** identifier for an element. No two elements on the page should have the same id. 

#### <a name="next-step"></a>What comes next?

We now have a basic HTML page. To see how our web page actually looks, we can either download the `helloworld.html` file, or copy-paste the provided code into a text editor of your choice (Note Pad, TextEdit, Sublime Text, etc.) and save the file with a ".html" extension. After doing so, we can open our html file on a web browser like Chrome, Firefox, etc. to see our page. 

> Try adding and removing elements in the page, adding and removing content inside the body tag, changing the title of the page, and more, to see what happens. Don't be afraid to ask questions or seek answers online!


## <a name="format"></a>Formatting in HTML

Before we discuss the various elements provided in HTML to define different kinds of information, we need to discuss two basic types of display values: **Block and Inline**. In HTML, each element has a default display value depending on the kind of element. This will have more significance when we start styling our pages, but it is good to start thinking about this early.

- **Block Elements** are those that are separate from the flow of the page. They are easy to move around and treat as separate entities from the whole page. Common examples of block elements include: paragraph `<p>`, heading tags `<h1>, <h2>... <h6>`, horizontal rule `<hr>`, table `<table>`, etc.  
- **Inline Elements** are those that are within the flow of the page. All inline elements affect each other because they, by default, are stuck next to each other. Common examples of inline elements include: anchor `<a>`, span `<span>`, image `<img>`, etc. 

#### <a name="text-format"></a>Text Formatting

- Paragraph `<p>` is a block element. Everything within the opening and closing paragraph tags is marked as one paragraph. 
- Heading tags are block elements. There are 6 levels of headings, with predefined styling, such that `<h1>` is the largest/highest level heading, `<h2>` is one below that, and so on till the smallest subheading `<h6>`. 
- Bold text is defined using the `<b>` or the `<strong>` tag. Both are inline tags. 
- Italics text is defined using the `<i>` or the `<em>` tag. Both are inline tags.
- Subscript `<sub>` is used to define subscripted text. It is an inline tag. 
- Superscript `<sup>` is used to define superscripted text. It is an inline tag. 
- Header `<header>` defines the header of the page. 
- Footer `<footer>` defines the footer of the page. 
- Section `<section>` defines a section of the page. 

## <a name="help"></a>Online Help and Resources

- [W3Schools](https://www.w3schools.com/html/default.asp) is a great website to learn more about HTML. It has definitions of all HTML tags, across versions of HTML, as well as example code, and some interactive environments or exercises you can use to learn beyond what is covered here. 
- 