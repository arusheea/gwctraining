# HTML Basic Guide 

HTML is the first step to building a web page. In this module, you will get a basic introduction to what HTML is and see some samples HTML web pages. 

### Contents 

- [Introduction: What is HTML?](#intro)
- [Basics of an HTML page](#minimum)
	- [What is an HTML tag?](#tags)
	- [What is the head tag?](#head-tag)
	- [What is the body tag?](#body-tag)

## <a href='#intro'></a>Introduction: What is HTML?

- HTML is short for Hyper Text Markup Language. This means, HTML is used to define our web page's markup, or in simpler terms, to define content formatting. 
- It's primary purpose is to define and label all the content on a web page. HTML can tell us what the title of a page should be, what our headings and subheadings are, what sections and links our page contains. 
- *It is important to note that HTML is **not** meant to alter the way our page looks*, i.e. it is not used for design purposes. For design, we will be using [CSS or Cascading Style Sheets](), which will be introduced in the next module.

## <a href='minimum'></a>Basics of an HTML page 

Refer to the following code or look at `helloworld.html` in this directory. We will now walk through the very basic requirements of an HTML page. 

```
<!DOCTYPE html>
<html>
  <head>
  	<meta charset='UTF-8'>
  	<title>My First HTML Page</title>
  </head>
  <body>
  	Hello World
  </body>
</html>
```

#### <a href='#tags'></a>What is an HTML tag? 

- An HTML tag or element is an item within angular brackets, for e.g. `<html>`, `<head>`, etc. 
- HTML tags are often in pairs, with an opening tag and a closing tag. Closing tags are usually the same as the opening tag, but with a / after the &lt; and before the tag name. In the provided code, you can see that `<html>` has the closing tag `</html>`. 
- HTML Tags or elements are used to define content elements on the page. 

#### <a href='#head-tag'></a>What is the head tag? 