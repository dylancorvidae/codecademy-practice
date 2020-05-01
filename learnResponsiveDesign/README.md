# Learn Responsive Design Course

## Em

Historically, the em represented the width of a capital letter M in the typeface and size being used. That is no longer the case.

Today, the em represents the size of the base font being used. For example, if the base font of a browser is 16 pixels (which is normally the default size of text in a browser), then 1 em is equal to 16 pixels. 2 ems would equal 32 pixels, and so on.

``` 
.splash-section {
  font-size: 18px;
}

.splash-section h1 {
  font-size: 1.5em;
} 
```

The example above shows how to use ems without relying on the default font size of the browser. Instead, a base font size (18px) is defined for all text within the splash-section element. The second CSS rule will set the font size of all h1 elements inside of splash-section relative to the base font of splash-section (18 pixels). The resulting font size of h1 elements will be 27 pixels.
