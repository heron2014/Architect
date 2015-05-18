# What are some best practises around manipulation and adding elements dynamically?

### All scripts, that are not necessary for rendering the DOM for the first time, should only be loaded once they are actually being used. 
This is to reduce the site loading time. Javascript by default blocks the parser.If the site initialisation takes a lot of effort, consider splitting up the init in different phases.
Manipulating and adding elements should be done asychronously, which means not inside document.ready() or document.onLoad() .

jQuery selectors can be stored in variables, in order to prevent jQuery from having to go through the DOM every time you use a certain element:

		jQuery('#justadiv').text('Hoi');
		jQuery('#justadiv').css('display', 'block');

		-> var justadiv = jQuery('#justadiv');
		justadiv.text('Hoi');

		etc....

### Graceful degradation
Ensure that your web pages still works without JavaScript.

### Unobtrusive JavaScript
Separate structure from behavior.

### Backwards compatibility
Ensure that older browsers don't choke on your scripts.

### Avoid mixing with other technologies
When you want to hide all elements with a certain class, use javascript to append a ".hide" class, rather than changing the actual css of the element.

### Optimize loops
One of the most common mistake is to read the length attribute of an array at every iteration. This means that every time the loop runs, JavaScript needs to read the length of the array. You can avoid that by storing the length value in a different variable. Another thing to ensure is that you keep computation-heavy code outside loops. This includes regular expressions and — more importantly — DOM manipulation. You can create the DOM nodes in the loop but avoid inserting them into the document. 

### Keep DOM access to a minimum
Accessing the DOM in browsers is an expensive thing to do. The DOM is a very complex API and rendering in browsers can take up a lot of time. You can see this when running complex web applications when your computer is already maxed out with other work — changes take longer or get shown half way through and so on.
To make sure that your code is fast and doesn’t slow down the browser to a halt try to keep DOM access to a bare minimum. Instead of constantly creating and applying elements, have a tool function that turns a string into DOM elements and call this function at the end of your generation process to disturb the browser rendering once rather than continually.

### Don’t trust any data
This is not only about evil people wanting to hack your systems; it starts with plain usability. Users will enter incorrect data, all the time. Not because they are stupid, but because they are busy, distracted or the wording on your instructions is confusing them. For example, I just booked a hotel room for a month rather than six days as I entered a wrong number … I consider myself fairly smart.
In short, make sure that all the data that goes into your systems is clean and exactly what you need. This is most important on the backend when writing out parameters retrieved from the URL. In JavaScript, it is very important to test the type of parameters sent to your functions (using the typeof keyword). 

### Add functionality with JavaScript, don’t create too much content
Try and avoid adding content with innerHTML(). Using an HTML template and loading this template via Ajax makes much more sense.

### Build on the shoulders of giants
It’s a good idea to learn JavaScript without libraries first, so you really know what’s going on, but you should make use of a JS library when you start developing web sites. You’ll have less issues to deal with and at least the bugs that appear will be ones that can be reproduced — not random browser issues.

### Utilize Proper Events and Callback Functions
You'll have access to the state of the request i.e. whether the request was successful; met with an error and finally whether it has been completed. Make proper use of these events and their respective callbacks to manipulate the UI for a better user experience. For example, if the request was unsuccessful, you'd want to update the user interface to reflect that their changes weren't successful while if it was successful, you'd want to tell them so. Don't keep the user waiting!

### Choose the Right Format for the Job
JSON? XML? HTML? Raw strings?

### Change the DOM Intelligently
So, for a chunk of HTML like so:
```HTML
<div id="container">
<span id="elem1"></span>
<span id="elem2"></span>
</div>
```
instead of doing this:
```javascript
$("#elem1").html("Value 1");
$("#elem2").html("Value 2");
```
Do this:
```javascript
var updatedText = "<span id=\"elem1\">Value1</span>
<span id=\"elem2\">Value2</span>";
$("#container").html(updatedText);
```

### General Coding guidelines:

* Use shortcut notation when it makes sense
* Avoid global Variables, in order to prevent overwriting variables
* Modularize — one function per task
* Avoid heavy nesting
* Comment as much as needed but not more


##### Sources:
* http://www.w3.org/wiki/JavaScript_best_practices
* http://domscripting.com/book/sample/
* http://code.tutsplus.com/tutorials/24-best-practices-for-ajax-implementations--net-9180
