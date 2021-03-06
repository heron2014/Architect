# What is DOM?

The Document Object Model (DOM) is a programming interface for HTML and XML document.
In other words any Web page is a document, which can be displayed in the browser window or as a HTML,source code. The Document Object Model provides another way to represent, store and manipulate that same document.

DOM looks like a giant tree, the elements in DOM are arranged in a hierarchy that defines what you eventually see in the browser. 

![DOM elements](http://i.imgur.com/VA7Shfj.png)

This hierarchy is used to help organize your HTML elements. It is also used to help your CSS style rules make sense of what styles to apply on which elements. 
From the JavaScript angle, this hierarchy helps to manipulate the DOM.

![DevTool with DOM rendered](http://i.imgur.com/EX1EQ8p.jpg)


##Finding your way around

Before you can find elements and do awesome things with them, you need to first get to where the elements are. The easiest way to tackle this topic is to just start form the top and slide all the way down.

At the top of the DOM tree are window and document objects which are global properties.
The window object represents something like the browser, and the document object is the root of the document.
DOM have at least one combination of parents, siblings, and children to rely on. To visualize this, take a look at the row containing the div and script elements in the following diagram:

![picture of DOM elements](http://i.imgur.com/yLovB8Z.png)

Both the div and script elements are siblings. The reason they are siblings is because they share the body element as their parent. The script element has no children, but the div element does. The img, h1, p, and div are children of the div element, and all children of the same parent are siblings as well. 



The following is a brief list of common APIs in web and XML page scripting using the DOM.
* document.getElementById(id)
* element.getElementsByTagName(name)
* document.createElement(name)
* parentNode.appendChild(node)
* element.innerHTML
* element.style.left
* element.setAttribute
* element.getAttribute
* element.addEventListener
* window.content
* window.onload
* window.scrollTo
