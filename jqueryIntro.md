Objectives

Download and include jQuery into an HTML document.
Find an element by id, tag name, class name, and more advanced selectors using jQuery.
Set an element’s text content and attributes using jQuery.
Set an element's CSS styles using jQuery.
Construct and add elements to the DOM using jQuery.
Remove elements from the DOM using jQuery.
Traverse the DOM using jQuery.
jQuery is a fast, small, and feature-rich JavaScript library. It makes things like HTML document traversal and manipulation, event handling, animation, and Ajax much simpler with an easy-to-use API that works across a multitude of browsers. With a combination of versatility and extensibility, jQuery has changed the way that millions of people write JavaScript.
jQuery is a widely popular library for manipulating the DOM in a browser.

What's wrong with vanilla JS?

Depending on who you ask, nothing! There's nothing you can do in jQuery that you can't do in plain old vanilla JavaScript. And as Javascript evolves, some feel like the gap between vanilla JavaScript and the enhancements of jQuery is narrowing.

But based on what you've seen so far, here are a few reasons you might like jQuery:

The syntax is shorter. This means you can write code expressing the same functionality more efficiently. Suppose we wanted to set an attribute to a div with an id of foo. In vanilla JavaScript, that code would look something like this:

document.getElementById('foo').setAttribute('attribute', 'value');
In jQuery, the same functionality looks like this:

$("#foo").attr('attribute', 'value');
This efficient interface also allows chaining calls so that we can combine multiple lines of vanilla JavaScript into one line using jQuery.

Return values from functions like document.getElementsByTagName or document.querySelectorAll are NodeLists, which are array-like objects which lack much of the functionality that arrays have. Specifically, array methods like forEach, map, etc. don't exist on these.

To address this issue, jQuery comes with an $.each method and a $.map method that lets us iterate over jQuery objects. The syntax is a bit different than with forEach and map, but we'll cross that bridge later.

Dealing with adding, removing, and toggling classes is a bit more streamlined in jQuery.

AJAX with jQuery is way better than AJAX with vanilla JavaScript. (More on this next week.)

Installation

You can download and include jQuery with a <script> tag in your HTML. There are also many CDNs available you can link to so you do not have to download the file.

Key Features

So why is jQuery so popular? What features does it offer that makes it so prevalent?

jQuery places 2 variables into the global scope for you to use: $ and jQuery. These two functions are identical. By convention you will see most people using $.

DOM Selection

The first thing that is necessary to be effective with jQuery is jQuery Selectors. Think back to functions like getElementById() and getElementsByClassName() and recall how these interact with the DOM and return nodes. jQuery has its own selectors that behave in similar ways. While you may be thinking, Don't we have querySelector and querySelectorAll? Keep in mind two things:

jQuery was released before querySelector and querySelectorAll (I know, right?!). It had its own engine built in to analyze the queries.
jQuery has even more expressive selectors than querySelector and querySelectorAll.
One of the nice things about jQuery selectors is you select DOM elements the same way you write CSS selectors. We can select nodes in the DOM that have IDs with the following syntax:

var $box = $('#box')
This assumes there is an ID of box somewhere on the page. It will return a jQuery object. This jQuery object is different than the node that gets returned with getElementById in that a jQuery object has other jQuery methods on it.

Selecting nodes in the DOM by class:

var $boxes = $('.box')
There are tons more selectors you can use and chain to find exactly the nodes you need.

HTML Tree

DOM Creation

jquery

Creating DOM elements with jQuery is super easy! Just insert a tag into the $ function. It should be able to handle any valid HTML string.

var myDiv = $('<div class="active">');
Attributes/CSS/Display

Modifying a DOM element can be difficult at times using native functions. jQuery offers a plethora of methods to make modifying the DOM super simple.

.toggleClass()

jquery

Say you have a DOM element with the className "box active red big". How would you detect and remove the class active from the middle of the string if it exists and add it if it doesn't exist? Fortunately with jQuery you can just use .toggleClass() to do that for you.

$('#myButton').click(function () {
    $(this).toggleClass('active')
})
.attr()

jquery

Use .attr() to change a DOM element's attribute:

console.log($('img').attr('title')) // print out the first img's title
$('img').attr('title', 'image hover text for the win!'); // set the title text on all images
.text()

jquery

Use the .text() function to get and set the text content on the element.

.val()

jquery

Use the .val() function to get and set the value on the element (usually used for an input's value property).

.html()

jquery

Use the .html() function to get and set the html inside an element. This is useful when making a change inside an element that's composed of multiple elements.

.css()

jquery

Use .css() to change the style attribute of a DOM element:

var color = $('div').css('background-color'); //get the first div background-color
$('div').css('background-color', 'red'); //set all div's background colors
.prop()

jquery

Use .prop() to change a property of a DOM element:

var isChecked = $('input[type="checkbox"]').prop('checked');
$('input[type="checkbox"]').prop('checked', true);
.height(), .innerHeight(), .outerHeight()

jquery

Use .height() to get the height of the content area.

jquery

Use .innerHeight() to get the height of the content area including the padding.

jquery

Use .outerHeight() to get the height of the content area including the padding and border (the margin is optional).

.width(), .innerWidth(), .outerWidth()

jquery

Use .width() to get the height of the content area.

jquery

Use .innerWidth() to get the height of the content area including the padding.

jquery

Use .outerWidth() to get the height of the content area including the padding and border (the margin is optional).

.offset()

jquery

Use .offset() to get the left and top coordinates (in pixels) of an element in relation to the document.

.position()

jquery

Use .position() to get the left and top coordinates (in pixels) of an element in relation to the offset parent, that is, the parent that is closest positioned element (that is with a position CSS property equal to relative, absolute, or fixed).

.offsetParent()

jquery

Use .offsetParent() to get the offset parent of an element. This is useful in identifying the element for which position() is based off of.

.scrollTop(), .scrollLeft()

jquery

Use scrollTop() to get the number of pixels we have scrolled from the top.

jquery

Similarly, scrollLeft() produces the number of pixels we have scrolled from the left.

DOM Manipulation

.prepend() .append() .insertBefore() .insertAfter() .before() .after()

All of these methods are used for inserting a DOM element into the DOM at various spots.

.prepend() and .append() insert as the first and last child of the target element.

.insertBefore() and .insertAfter() insert before or after as siblings of the target element.

.before() and .after() are the same as .insertBefore() and .insertAfter().

.remove(), .detach()

remove

The .remove() function removes a DOM element from the DOM.

detach

The .detach() function is very similar to .remove(), but it returns the removed jQuery object that you can use later.

.clone()

clone

The .clone() function makes a deep copy clone of the selected DOM element.

.empty()

empty

the .empty() method will clear out the contents of any DOM element.

$('div').empty() //clear out all divs
.replaceAll(), .replaceWith()

replaceWith

Use replaceWith to replace a source element with a target element.

replaceAll

Use replaceAll to replace all the target elements with a source element.

DOM Traversing

.get()

get

Use .get() with an index to get an item out of the jQuery collection that is the native DOM element.

.eq()

eq

Use .eq() with an index to get an item out of the jQuery collection that is a jQuery object.

.parent(), .parents()

parent

Use .parent() to get the parent element.

parents

Use .parents() to get all the parents element to a particular element.

.children()

children

Use .children() to get the children of an element. It goes only one level deep.

.first(), .last()

first

Use .first() to get the first child.

last

Use .last() to get the first child.

.find()

find

Use .find() to search through the children of an element. It goes all the way into the tree.

.next(), .nextAll(), .prev(), .prevAll(), .siblings()

next

Use next() to get the next sibling.

nextAll

Use nextAll() to get all the siblings after the element.

prev

Use prev() to get the previous sibling.

prevAll

Use prevAll() to get all the siblings before the element.

siblings

Use siblings() to get all the siblings of an element.

.has()

jquery
Use .has() to filter the set by a selector.

.is()

jquery
Use .is() to check if the matched set matches a specific selector.

.not()

jquery
Use .not() to remove items from the set of match elements by a selector or function.

.filter()

jquery
Use .filter() to only include items from the set of match elements by a selector or function.

.closest()

jquery
Use .closest() to get the closest element by checking itself and all of its ancestors.

Other awesome Methods

.show(), .hide(), .toggle()

jquery
jquery
jquery
.animate()

jquery
.fadeIn(), .fadeOut()

jquery
jquery
.slideDown(), .slideUp()

jquery
jquery
Further reading

jQuery docs
jQuery CheatSheet
You might not need jQuery
jQuery Playground
http://jqfundamentals.com/chapter/jquery-basics
Further Practice

https://github.com/gSchool/boxes-jQuery-playground
exercise 00 on https://github.com/gSchool/jquery-exercises
https://github.com/gSchool/jquery-calculator
https://github.com/gSchool/jquery-image-filtering
http://howto.galvanize.com/tutorials/2015-05-15-javascript-filtering/
http://howto.galvanize.com/tutorials/2015-05-07-javascript-inbox/
http://howto.galvanize.com/tutorials/2015-05-27-javascript-weather-app/
https://github.com/gSchool/itunes_song_guessing_game
https://github.com/gSchool/githubProfileClone
https://github.com/gSchool/jQuery-Practice/
Slides

Slides
