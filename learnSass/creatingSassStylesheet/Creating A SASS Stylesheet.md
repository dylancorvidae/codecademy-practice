# Learn SASS - Creating A SASS Stylesheet

## Why Sass?
Sass, or Syntactically Awesome StyleSheets, is an extension language for CSS. With Sass, you can write clean, sustainable CSS code and solve the common repetition and maintenance challenges present in traditional CSS.

In addition to being a valuable skill for any front-end developer, transitioning from CSS to Sass is pretty smooth due to the familiar syntax. For this reason, we will be learning the SCSS (Sassy CSS) syntax.


## Compiling Sass
Sass can’t be directly interpreted by your browser, so it must first be converted, or compiled, to CSS before the browser can directly understand it.

Compiling refers to converting code to lower level code so that it can be executed. By compiling SCSS to CSS, it can be interpreted by your browser and the results will appear on a webpage.

Before we dive into writing Sass, let’s first learn how to compile it to CSS by typing the following command in the terminal and pressing enter:

sass main.scss main.css
The sass command above takes in two arguments:

The input (main.scss)
The location of where to place that output (main.css)


## Sass: Overview
Let’s get started! Sass has many perks that enable us to write succinct, readable code. In this lesson we will explore three concepts:

Variables
Mixins
Nests


## Nesting Selectors
The first Sass construct we will learn about is nesting.

Nesting is the process of placing selectors inside the scope of another selector:

In programming, a variable’s scope is the context in which a variable is defined and available to use.

In Sass, it’s helpful to think of the scope of a selector as any of the code between its opening { and closing } curly brackets.

Selectors that are nested inside the scope of another selector are referred to as children. The former selector is referred to as the parent. This is just like the relationship observed in HTML elements.
```
.parent {
  color: blue;
  .child {
    font-size: 12px;
  }
}
```
In the example above .child is the child selector and .parent is the parent selector.

The above SCSS would compile to the following, equivalent CSS:
```
.parent {
  color: blue;
}

.parent .child {
    font-size: 12px;
}
```
Nesting allows you to see the clear DOM relationship between two selectors while also removing the repetition observed in CSS.


## Nesting Properties
Congrats, you’ve written your first nested selectors!

In SCSS, nesting is not limited only to selectors. You can also nest common CSS properties if you append a : colon suffix after the name of the property.

For example, the following SCSS code:
```
.parent {
  font : {
    family: Roboto, sans-serif;
    size: 12px;
    decoration: none;
  }
}
```
will compile to the following CSS:
```
.parent {
  font-family: Roboto, sans-serif;
  font-size: 12px;
  font-decoration: none;
}
```


## Variables In Sass
Variables in SCSS allow you to assign an identifier of your choice to a specific value.

Why is that useful? Unlike in CSS, if you need to tweak a value, you’ll only have to update it in one place and the change will be reflected in multiple rules.

In Sass, $ is used to define and reference a variable:
```
$translucent-white: rgba(255,255,255,0.3);
```
Note: It’s important to stick to one naming convention for variables when you first build out your codebase. This will help you reference them easily in the future.


## Sass(y) Types
There are different data types you can assign to a variable in CSS.

In addition to the color data type we have seen, there are also:

1. Numbers, such as 8.11, 12, and 10px. Notice that while 10 has a unit of px associated with it, it is still considered a number.

2. Strings of text, with and without quotes. Some examples are "potato", 'tomato', span.

3. Booleans, or simply true and false.

4. null, which is considered an empty value.


## Maps & Lists
In addition to color, numbers, strings, booleans, and null, Sass also has two other data types, lists and maps.

Lists can be separated by either spaces or commas. For example, the following list denotes font properties, such as:
```
1.5em Helvetica bold;
```
or
```
Helvetica, Arial, sans-serif;
```
Note: You can also surround a list with parentheses and create lists made up of lists.

Maps are very similar to lists, but instead each object is a key-value pair. The typical map looks like:
```
(key1: value1, key2: value2);
```
Note: In a map, the value of a key can be a list or another map.


## Generalizations
Congratulations! You completed your first Sass StyleSheet and learned some powerful new concepts:

1. Nesting is the process of placing child selectors and properties in the scope of a parent selector. This allows a programmer to draw DOM relationships and avoid repetition.

2. Variables make it easy to update code and reference values by allowing you to assign an identifier to a value.

3. Sass Data Types include:

Numbers
Strings
Booleans
null
Lists
Maps
Nesting and variables are just two ways that Sass keeps stylesheets clean. In the next unit, you’ll learn about other Sass constructs that serve the same purpose.