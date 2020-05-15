# Sassy Parallax Banner
Parallax scrolling is a popular web design trend that gained momentum in recent years! If you’ve ever noticed a background moving at a slower rate than the foreground, creating a 3D effect and adding depth, then you’ve seen parallax scrolling.

The sleek traveling agency Travels-R-Us has reached out to you to launch their new “Visit Myanmar” page. They have requested a page that implements a parallax banner so that the user may scroll and admire travel photography as they decide where to take their next trip. After some research, you decide nesting, variables, and mixins will be the best tools to style a parallax banner. Let’s do this!

If you get stuck during this project or would like to see an experienced developer work through it, click “Get Help“ to see a project walkthrough video.


## Tasks
1. Define the following variables at the top of your main.scss file—:
```
$parallax-height: 100vh;
$center-margin: 0px auto;
Reference those variables inside the instances that use them.
```
2. Start to create the logic for a parallax effect. Inside of both id selectors for our background parallax, #landscape and #monkeys add the following properties:
```
  width: 100%;
  height: 100vh;
  perspective: 1px;
  transform: translateZ(-1px);
  overflow-x: hidden;
  overflow-y: auto;
```
3. Since you are incl ding travel photography in your parallax, you make sure that the background image covers the entire div. You can do this by setting the webkit-background-size to a value cover. This property is vendor specific, so it means you will need to make a mixin with the following properties:
```
    background-size: cover;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
```
The mixin should takes one parameter, the size, and assign that to all of the vendor properties.

4. Task 4: At the top of your main.scss, make a new mixin with the rest of the parallax background properties.
```
@mixin parallax-background($file) {
  background: url($file) no-repeat center center fixed;
  @include background-size(cover);
}
```
5. Include the mixin inside the selectors of the both #landscape and #monkey, passing in a value of “https://s3.amazonaws.com/codecademy-content/projects/sass/landscape.jpg" and “https://s3.amazonaws.com/codecademy-content/projects/sass/monkeys.jpg" respectively.

6. Assign the h1 property a
```
transform: translateZ(-2px);
```
This is to ensure that the Z-axis may be at a different translate setting than the image in the foreground.

7. Scroll around in the webpage! Observe the parallax effect. Tweak the transform effects as you please and play around with the values to create your own effects.