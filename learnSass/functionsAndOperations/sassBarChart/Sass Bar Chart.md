# Sass Bar Chart

The team at Organic-Press wants to include a static bar chart on their about page displaying the top 10 produced foods in the world. The company would prefer it if you accomplished this task using no Javascript. Your first order of business is to create this barchart using only HTML and SCSS variables, functions, and loops.

## Tasks

1. Analyze the $top-foods variable, a list of lists. Each object in the list is a list of two elements: a string denoting a food, and a number of tonnes produced. This is the data we will be representing in our bar chart.

2. In index.html, add ten <rect></rect> svg elements! These are going to be our bars.



3. In index.html, add the h1 one element above all the rects, denoting the food item of the data displayed:
```
<h1>Top Ten Most Produced Foods in the World, by Tonnes</h1>
```

4. Our html setup is complete, let’s get styling! In main.scss, include an @each loop that traverses the best selling list for each “food” and “tons produced”:
```
@each $food, $tons-produced in $top-foods{

}
```
Leave the body of the loop empty for now!



5. The first thing you will want to do inside your loops is to make sure you have access to the position of each element on the list.

Do this by using the index Sass function, which returns the position of an element in a list.

The index functions takes two arguments: index($list, $element). Your element in this case will be ($foods $tons-produced), and your list will be $top-foods. Assign the index to a variable $i:
```
$i: index($top-foods,($food $tons-produced));
```

6. Next, you’ll want to make sure you make use of the rect:nth-child() css selector by assigning it the value of $i in string interpolation notation in main.scss.
```
rect:nth-child(#{$i + 1}) {

}
```

7. Now we can actually begin styling each of the bars, or <rect> elements in our document. Let’s make those bars data-driven by basing their height on the amount of food produced. You will want to use string interpolation so you can assign the $tons-produced as the value in pixels divided by three. This is because otherwise it is too tall to fit in the viewport. Add the following in main.scss inside your rect:nth-child(#{$i}):
```
height: #{$tons-produced/3}px;
```

8. Display the name of the food on each bar by using the :before pseudo element and assigning the content property a value of $food inside of main.scss. This will make the content of the element be a string with the value of the food.
```
&:before {
  content : $food;
}
```

9. In addition to the food, we also want to be sure and display the number of tons produced. Let’s use the :after pseudo element to do that. Assign its content property a value of $tons-produced. Since the numbers are in units, concatenate an m to symbolize a million.
```
&:after {
  content: $tons-produced + "m";
}
```

10. Ring ring! Last minute call from the team at FabFiction asking for a slight design change. They want to color their bar charts, and not just any kind of color, but an “ombre” effect from the first bar to the last. They want their brand colors, three shades of blue, to fade out from the first bar chart to the last.

In main.scss write an if statement with three branches, an @if, @else-if and else to check if the index modulus three is equal to zero, one, or otherwise (two). Leave the body of each statement empty for now.
```
@if($i % 3 == 0){
  // some rule
}@else if($i % 3 == 1){
  //some rule
}@else{
  //more rules
}
```

11. Sweet, now we can define the fading out ombre effect as a function of the index using the handy-dandy function fade-out. Use fade-out($color, $i*5/100); and assign $sea-green, $pale-green, and $diamond-blue to @if, @else-if, and @else respectively.



12. Great job! You’ve accomplished a stylish static bar chart using only HTML and SCSS.

Note: In most scenarios, the data you assign to a bar chart would be coming from a dynamic source in your JavaScript files. In doing this with pure SCSS you have exercised your @each, conditional, and color function skills. 