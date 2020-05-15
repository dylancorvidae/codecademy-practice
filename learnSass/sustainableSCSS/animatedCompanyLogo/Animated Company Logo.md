# Animated Company Logo
The team at Logo Factory wants you to animate a new Sass logo using SCSS. The instructions include making the text slide in from the left as it appears on the screen and having the circle in the logo change opacity as it appears behind the letters. To start you off, we’ve provided some terribly formatted SCSS. It’s your job to clean it up. You must determine when it’s best to make a mixin or extend a placeholder, as well as how split up the logic into partials.

If you get stuck during this project or would like to see an experienced developer work through it, click “Get Help“ to see a project walkthrough video.


## Tasks

1. Let’s organize logic first. The @import statements should always be at the top of your main.scss stylesheet. Move the font imports to the top of the file.

Hint
```
@import url(https://fonts.googleapis.com/css?family=Open+Sans);
Place the following at the top of your file.
```
2. Next, split up all variables inside their own partial. Right now you can find the four variables in the middle of the file. Paste those inside the helper/_variables.scss partial.

Hint
```
$slogan-font: 'Open Sans', sans-serif;
$slogan-spacing: 0.183em;
$blue: #204056;
```

3. Import the variables partial at the top of your main.scss file.

Hint
```
@import "helper/variables";
```
4. The animations for our text are also spread throughout the file. Centralize that logic inside the helper/_animations.scss partial. The two animations are appear and slide-left. Find them and move them their contents inside the file.

Hint
```
@-webkit-keyframes appear {
  0%   { opacity: 0; }
  100% { opacity: 1; }
}
```
and
```
/* Chrome, Safari, Opera */
@-webkit-keyframes slide-left {
    from {left: 0%;}
    to {left: 40%;}
}
```
5. Import the animations partial at the top main.scss.

Hint
```
@import "helper/_animations.scss";
```
6. Fix the mixin misuse. Notice that the mixin slide-left does not take any parameters. Since it’s never directly used in the html, make this class a placeholder and place it inside the placeholder partial, helper/_placeholders.scss.

Hint
```
%slide-left{
  animation: slide-left 5s;
  -webkit-animation: slide-left 5s;
}
```
7. Import the placeholders partial at the top of main.scss.

Hint
```
@import "helper/placeholders";
```
8. Replace all instances that included the mixin by instead extending the new placeholder.

Hint
```
@extend %slide-left;
```