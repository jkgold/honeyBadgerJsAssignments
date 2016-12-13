Intro to the DOM Part I: Introduction

Objectives

By the end of this article you should be able to:

Explain the relationship between the DOM and HMTL.
Explain what the DOM is.
What is the document.
Explore and interact with the DOM using browser dev tools.
An Introduction to the DOM

What is the DOM

Every web browser has something called the DOM, where DOM is an acronym for Document Object Model.

The DOM is an API, where API is an acronym for Application Programming Interface. Simply put, an API is a way for programs to interact with each-other.

That's a lot of technical jargon, so let's just illustrate what an API is with an example.

Let's say I wrote a program named fs in the language C++. The program could read and write files to a computer's filesystem. I also wrote an API that allowed other programs to tell fs to read and write files.

You are writing a program in Javascript for a client, and need it to read user settings from a file. Your Javascript code could use my fs API to tell my program to read and write files.

// use the fs API to tell the fs program to read settings.json
var userSettings = fs.readFile('/path/to/settings.json');
My fs API provided your program the ability to interact with the filesystem. It provided:

a way to read files from the filesystem.
a way to write files to the filesystem.
Similarly, the browser's DOM API provides other programs the ability to interact with the document. It provides:

a way to represent a document as an object.
a way to interact with a document.
What is a Document

So what is a document anyway?

The most commonly used document is a web page.

A document can be represented (modeled) in a number of ways:

A document can be textually represented via HTML (how the developer sees a web page).
A document can be visually represented via the browser window (how the user sees a web page).
A document can be digitally represented via the DOM (how the program sees a webpage).
Note: a web page doesn't just have to be HTML, it may also be:

XML
SVG
How the DOM models the document

The DOM models (represents) the document as an object.

Objects are nice because programs can interact with them easily. It would be hard if we had to interact with the document by having our programs read the HTML or use computer vision to interact with the browser window.

This isn't just any object, it is a special data structure known as a tree.

The data structure gets its name because it can be visually represented to look like a real world tree: a tree has a trunk, the trunk has branches, each branch can have more branches.

The data structure tree has a root node (trunk), the root node has nodes (branches), a node (branch) can have other nodes (branches).

The file system is a tree. The root directory / is the root node (trunk). It contains several other directories, each of these is a node (branch). Each of those directories contain other directories (nodes). Just like a directory:

A node contained in another node is known as the child node.
A node that contains another node is known as the parent node.
Let's walk through this HTML document:

<html>
  <head>
    <title>Some Title</title>
  </head>

  <body>

    <h1>Some Header</h1>

    <div>
      <p>text inside p inside div</p>
    </div>

  </body>
</html>
The document could be modeled as a tree:

A tree of the html above

Lets walk through it how the HTML maps to the tree:

The <html></html> tag becomes the root node.
It has 2 child nodes: <head></head>, <body></body
The <head></head> node has a child node: <title></title>.
The <body></body> node has 2 child nodes: <h1></h1>, <div></div>.
The <div></div> node has a child node: <p></p>.
Review

The DOM is a fully object-oriented representation of the web page, and it can be modified with a scripting language such as JavaScript.
The DOM (Document Object Model) is an API that provides programs with:

a model of the document as a tree.
a way for programs to interact with the document.
A document is a web page.

Interact using Dev Tools / Exercise

You Do:

In Chrome, press CTRL + ALT + I to open up your dev tools.
Navigate to the console tab of the dev tools.
Type document in the console.
Right click on #document and click view in elements panel.
On the right select the properties tab, this will list all the properties of the document object.
Click the #document to drop down the document node's properties.
Find the propertychildNodes and expand the html node.
Find the property childNodes and expand the body node.
List three of the properties you find here.
You Do:

In Chrome, right click on this text.
Click inspect.
On the right select the properties tab, this will list all the properties.
Open up the ol dropdown.
Look through the properties to find the child node.
Look through the properties to find the parent node.
Resources

The Basics of JavaScript DOM Manipulation
MDN: Introduction to the DOM
MDN: DOM Reference
MDN: Document API Reference(The document object)
Slides

Slides
Slides
Slides
Assignment

See https://github.com/gSchool/js-dom-tests.

Stretch Assignment

The Checkerboard Exercise
DOM Query
Style with JavaScript
For reference: MDN HTMLElement.style
Next Page

DOM Manipulation
