#CSS Best Practices

###1. Be consistent

CSS "best practices" are a matter of opinion, and everyone tends to establish their own guidelines. It is most important to be consistent: within your own code, and across a group, project or organisation. Consistent styling makes code more readable for yourself and others.

###2. Use an external stylesheet

Rather than mixing your HTML and CSS in one document, use an external stylesheet to separate content from presentation. A single stylesheet can be applied to every page of a site, allowing quick style changes to a single file.

External stylesheets can be cached, allowing faster page loading times

###3. Use multiple stylesheets

Depending on the complexity of the design and the size of the site, it’s often easier to make smaller, multiple stylesheets instead of one giant stylesheet. Using multiple stylesheets makes it easier for the designer to manage the project.

Using multiple stylesheets will also speed up your site, since it will only load required CSS for a single page rather than all CSS styles for your site.

###4. Create a master stylesheet

For a large, complex project, it might be useful to create a "master stylesheet" to standardise styling across pages. This stylesheet can contain common elements to every page (eg. font, heading styles). Since you don't have to repeat the CSS in other files, it makes the code leaner and faster to load.

###5. Create your HTML document first

Starting with a complete HTML document makes it easier to then structure your CSS styling. You'll be able to organise the styling properties according to the order of HTML elements.

###6. Organise documents with a top-down structure

It's important to lay out your stylesheet in a way that allows you to quickly find parts of your code. Many people recommend a "top-down" format. This structure tackles styles as they appear in the source code. 

An example stylesheet might be ordered like this:
* Generic classes (body, a, p, h1, etc.)
* header
* nav-menu
* main-content

###7. Name your classes and IDs sensibly

Some tips for naming classes and IDs:
Name classes and IDs in ways that clearly describe its function -- using shorthand will make your code confusing to others, and possibly yourself
Use hyphens not underscores in div names (eg. "hero-image" not "hero_image")
Avoid using IDs like "column-right" or "column-left", that become redundant if you want to move the elements around -- instead use "column-alpha", "column-beta"

###8. Be as specific as possible with selectors

Use the most specific selector wherever possible, especially classes and IDs if available. This makes your code more readable and speeds up loading times.

"Descendent selectors" can slow down your code significantly. They look like this:
div p {
  ⋮ declarations
}
Since CSS selectors are read right to left, using code like this is an expensive process. In this instance, the browser will first search the entire document for all instances of "p" before finding "div p".

Don't do this! Instead, use a specific class or ID, or use a "child selector". Child selectors look like this:
div > p {
  ⋮ declarations
}
The '>' indicates that the browser should first search for "div" before centring in on "div p" (a more efficient way of sorting through the code).

###9. Combine CSS properties for multiple elements

If you find yourself adding the same style properties to multiple selectors, combine them into one section, or create a class.

###10. Use shorthand CSS properties

Instead of:
h1 {
  margin-top : 5px;
  margin-left : 10px;
  margin-bottom : 15px; 
  margin-right : 20px;
}

use:
h1 {
   margin : 5px, 10px, 15px, 20px; // top, right, bottom and left values
 }
Comprehensive guide to CSS shorthand here:
http://www.dustindiaz.com/css-shorthand/ 


###11. Alphabetise your properties

Organising your properties in alphabetical order within selectors makes them easier to read and find.

For example:
.some-class{
  color: #fff;
  float: left;
  height: 200px;
  margin: 0;
  padding: 0;
  width: 150px;
}

###12. Add comments to your CSS

Add comments to your CSS to explain or signpost parts of your code to make it more readable.

###13. Keep a Class and Colour Reference

Keeping a library of your CSS classes is useful for debugging. A colour reference list is also useful to remember HEX codes and keep styling consistent.

###14. Run code through a CSS validator

Running your site through a validator will evaluate your CSS for compliance with W3C open standards
http://jigsaw.w3.org/css-validator/ 

###15. Run code through google page speed

Running your site through this google tool will identify elements of a page that are slowing it down: https://developers.google.com/speed/pagespeed/
