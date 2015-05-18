# What is DOM?

The Document Object Model (DOM) is a programming interface for HTML and XML document.
In other words any Web page is a document, which can be displayed in the browser window or as a HTML,source code. The Document Object Model provides another way to represent, store and manipulate that same document.
DOM is rendered in Dev Tools. 

(/images/dom-dom-dom.jpg)


DOM looks like a giant tree, the elements in DOM are arranged in a hierarchy that defines what you eventually see in the browser.

(/images/mapping_72.png)

This hierarchy is used to help organize your HTML elements. It is also used to help your CSS style rules make sense of what styles to apply on which elements. 
From the JavaScript angle, this hierarchy helps to manipulate the DOM.

##Finding Your Way Around

Before you can find elements and do awesome things with them, you need to first get to where the elements are. The easiest way to tackle this topic is to just start form the top and slide all the way down.

At the top of the DOM tree are window and document objects which are global properties.
The window object represents something like the browser, and the document object is the root of the document.

![picture of DOM elements](http://i.imgur.com/yLovB8Z.png)