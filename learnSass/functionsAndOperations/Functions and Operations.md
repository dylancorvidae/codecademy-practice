# FUNCTIONS AND OPERATIONS

## Functions in SCSS
Functions and operations in Sass allow for computing and iterating on styles.

With Sass functions you can:

Operate on color values
Iterate on lists and maps
Apply styles based on conditions
Assign values that result from math operations


## Arithmetic and Color
As mentioned, Sass specifically comes equipped with functions that make working with colors easier.

The alpha parameter in a color like RGBA or HSLA is a mask denoting opacity. It specifies how one color should be merged with another when the two are on top of each other.

- In Sass, the function fade-out makes a color more transparent by taking a number between 0 and 1 and decreasing opacity, or the alpha channel, by that amount:
```
   $color: rgba(39, 39, 39, 0.5);
   $amount: 0.1;
   $color2: fade-out($color, $amount);//rgba(39, 39, 39, 0.4) 
```
- The fade-in color function changes a color by increasing its opacity:
```
$color: rgba(55,7,56, 0.5);
$amount: 0.1;
$color2: fade-in($color, $amount); //rgba(55,7,56, 0.6)
```
- The function adjust-hue($color, $degrees) changes the hue of a color by taking color and a number of degrees (usually between -360 degrees and 360 degrees), and rotate the color wheel by that amount.


## Color Functions
Sass also allows us to perform mathematical functions to compute measurements— including colors.

Here is how Sass computes colors:

The operation is performed on the red, green, and blue components.
It computes the answer by operating on every two digits.
```
$color: #010203 + #040506;
```
The above would compute piece-wise as follows:
```
01 + 04 = 05
02 + 05 = 07
03 + 06 = 09
```
and compile to:
```
color: #050709;
```
Sass arithmetic can also compute HSLA and string colors such as red and blue.


## 