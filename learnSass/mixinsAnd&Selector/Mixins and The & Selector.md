# Learn SASS - Mixins and the & Selector

## The & Selector in Nesting
In the next set of exercises, you’ll use new Sass concepts to fix and add styles to the notecard on the right so that it flips when you hover over it!

Recall that, in CSS, a pseudo-element is used to style parts of an element, for example:

Styling the content ::before or ::after the content of an element.

Using a pseudo class such as :hover to set the properties of an element when the user’s mouse is touching the area of the element.

In Sass, the & character is used to specify exactly where a parent selector should be inserted. It also helps write psuedo classes in a much less repetitive way.

For example, the following Sass:
```
.notecard{ 
  &:hover{
      @include transform (rotatey(-180deg));  
    }
  }
```
will compile to the following CSS:
```
.notecard:hover {
  transform: rotatey(-180deg);
}
```


## What is a Mixin?
In addition to variables and nesting, Sass has multiple constructs that reduce repetition.

In Sass, a mixin lets you make groups of CSS declarations that you want to reuse throughout your site.

The notation for creating a mixin is as follows:
```
@mixin backface-visibility {
  backface-visibility: hidden;
  -webkit-backface-visibility: hidden;
  -moz-backface-visibility: hidden;
  -ms-backface-visibility: hidden;
  -o-backface-visibility: hidden;
}
```
Note: Mixin names and all other Sass identifiers use hyphens and underscores interchangeably. The following code:
```
.notecard {
.front, .back {
    width: 100%;
    height: 100%;
    position: absolute;

    @include backface-visibility;
  }
}  
```
is equivalent to the following CSS:
```
.notecard .front, .notecard .back {
  width: 100%;
  height: 100%;
  position: absolute;

   backface-visibility: hidden;
  -webkit-backface-visibility: hidden; 
  -moz-backface-visibility: hidden;
  -ms-backface-visibility: hidden;
  -o-backface-visibility: hidden;
}
```


## Mixins: Arguments
Mixins also have the ability to take in a value.

An argument, or parameter, is a value passed to the mixin that will be used inside the mixin, such as $visibility in this example:
```
@mixin backface-visibility($visibility) {
  backface-visibility: $visibility;
  -webkit-backface-visibility: $visibility;
  -moz-backface-visibility: $visibility;
  -ms-backface-visibility: $visibility;
  -o-backface-visibility: $visibility;
}
```
In fact, you should only ever use a mixin if it takes an argument. We will learn more about this in a later exercise.

The syntax to pass in a value is as follows:
```
@include backface-visibility(hidden);
```
In the code above, hidden is passed in to the backface-visibility mixin, where it will be assigned as the value of its argument, $visibility.


## Default Value Arguments
Mixin arguments can be assigned a default value in the mixin definition by using a special notation.

A default value is assigned to the argument if no value is passed in when the mixin is included. Defining a default value for each argument is optional.

The notation is as follows:
```
@mixin backface-visibility($visibility: hidden) {
   backface-visibility: $visibility;
  -webkit-backface-visibility: $visibility;
  -moz-backface-visibility: $visibility;
  -ms-backface-visibility: $visibility;
  -o-backface-visibility: $visibility;
}
```
In the example above, if no value is passed in when backface-visibility is included, hidden would be assigned to all properties.


## Mixin Facts
In general, here are 5 important facts about arguments and mixins:

Mixins can take multiple arguments.
Sass allows you to explicitly define each argument in your @include statement.
When values are explicitly specified you can send them out of order.
If a mixin definition has a combination of arguments with and without a default value, you should define the ones with no default value first.
Mixins can be nested.
Here are some concrete examples of the rules:
``
@mixin dashed-border($width, $color: #FFF) {
  border: {
     color: $color;
     width: $width;
     style: dashed;
  }
}

span { //only passes non-default argument
    @include dashed-border(3px);
}

p { //passes both arguments
    @include dashed-border(3px, green);
}

div { //passes out of order but explicitly defined
   @include dashed-border(color: purple, width: 5px); 
}
```
In the example above, the color of the border of span elements would be white, the border of paragraph elements would be green, while the div elements would have a thicker purple border.


## 