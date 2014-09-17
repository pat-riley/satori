#Sass

Sass is a CSS preprossesor. It compiles into CSS that you can then use on your website

##Variables

You can use variables to store any type of CSS value.

```
$font-stack:    Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
```

When the Sass is proccessed, it takes those variables and outputs the value.

##Nesting

Allows you to target elements with the same visual heirarchy as HTML.

	nav {
	  ul {
	    margin: 0;
	    padding: 0;
	    list-style: none;
	  }

	  li { display: inline-block; }

	  a {
	    display: block;
	    padding: 6px 12px;
	    text-decoration: none;
	  }
	}
	
And this is the output

	nav ul {
	  margin: 0;
	  padding: 0;
	  list-style: none;
	}

	nav li {
	  display: inline-block;
	}

	nav a {
	  display: block;
	  padding: 6px 12px;
	  text-decoration: none;
	}
	
	
##Partials

You can create partial Sass files that contain snippets of CSS that you can include in other Sass files.  This helps modularize your CSS and easier to maintain. 

####Naming
Partials always begin with `_`
	
	_partials.scss
	
####Importing
Css has an import option tha tlets you split your CSS into smaller portions, the problem is that when you use `@import` in CSS it creates another HTTP request. 

Sass builds upon the current CSS `@import` but instead of requiring an HTTP request, Sass will take that file that you want to import and combine it with the file you're importing so you can serve a single CSS file to the web browser. 

Import Sass partials into your main stylesheet with the following

	@ import ".../_partialname";

Import multiple Sass files like so

	@import
		"../sass/_header",
		".../sass/_footer";

##Mixins

A mixin lets you make groups of CSS declarations that you want to reuse throughout your site. You can even pass in values to make your mixins more flexible. Here is a an example using `border-radius`.

	@mixin border-radius($radius) {
	  -webkit-border-radius: $radius;
	     -moz-border-radius: $radius;
	      -ms-border-radius: $radius;
	          border-radius: $radius;
	}

	.box { @include border-radius(10px); }

To create a mixin, use the `@mixin` directive and give it a name. We've named our mixin `border-radius`. We're also using the `$radius` variable inside the parentheses so we can pass in a radius of whatever we want. After you create your mixin, you can then use it as a CSS decleration starting with `@include` followed by the name of the mixin.

##Extend/Inheritance

This is one of the most useful features of Sass. Using `@extend` lets you share a set of CSS properites from one selector to another. 

	.message {
	  border: 1px solid #ccc;
	  padding: 10px;
	  color: #333;
	}

	.success {
	  @extend .message;
	  border-color: green;
	}

	.error {
	  @extend .message;
	  border-color: red;
	}

	.warning {
	  @extend .message;
	  border-color: yellow;
	}

What the above code does is allow you to take the CSS properties in `.message` and apply them to `.success`, `.error`, & `.warning`. The magic happens with the generated CSS, and this helps you avoid having to write multiple class names on HTML elements. This is what it looks like:


	.message, .success, .error, .warning {
	  border: 1px solid #cccccc;
	  padding: 10px;
	  color: #333;
	}

	.success {
	  border-color: green;
	}

	.error {
	  border-color: red;
	}

	.warning {
	  border-color: yellow;
	}

##Operators

Doing math in CSS is very helpful. The standard operators are availible.

	.container { width: 100%; }

	article[role="main"] {
	  float: left;
	  width: 600px / 960px * 100%;
	}

	aside[role="complimentary"] {
	  float: right;
	  width: 300px / 960px * 100%;
	}

We've created a very simple fluid grid, based on 960px. Operations in Sass let us do something like take pixel values and convert them to percentages without much hassle. The generated CSS will look like:

	.container {
	  width: 100%;
	}

	article[role="main"] {
	  float: left;
	  width: 62.5%;
	}

	aside[role="complimentary"] {
	  float: right;
	  width: 31.25%;
	}





