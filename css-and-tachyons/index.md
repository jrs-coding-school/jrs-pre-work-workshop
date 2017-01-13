## Cascading Style Sheets Specification (CSS) and Tachyons

The Cascading Style Sheets Specification (CSS) is a computer language that is used to write formatting instructions ( rules ). These rules tell a web browser how webpage content should 'look'— in terms of: layout. position, alignment, width, height, etc.

For this course we will use [Tachyons](http://tachyons.io/), which is a CSS toolkit.  It provides 100% responsive web pages with as little css as possible.  

CSS allows your web page to look nice.  You can style the HTML elements on the page by controlling things like:

- Borders and Border Radius
- Fonts and Font sizes
- Spacing between elements.
- Text fonts and sizes
- Colors
- Animation

Responsive means your website should work regardless of a users device or screensize.

Tachyons makes your website readable.  No matter the lighting, or the device, font-sizes should be large enough and contrast should be high enough for your users to easily read your content.

Tachyons features a [spacing scale](http://tachyons.io/docs/layout/spacing/) based on powers of two. This is a common scaling system used in typography for 400 years.  

This means that 1rem equals the font size of the html element (which for most browsers has a default value of 16px).

> "A modular scale, like a musical scale, is a prearranged set of harmonious proportions."

## Common Tachyons CSS Classes

Before we list the Tachyons css classes, let's go over some basic terminology:

## Size and Length in css

CSS offers a number of different units for expressing length.  A common way to express size on a web page is with pixels or **px**. The **px** unit is the magic unit of CSS.  The **px** unit is defined to be small but visible, and such that a horizontal `1px` wide line can be displayed with sharp edges.   A photo with a 600 by 400 resolution will be `600px` wide and `400px` high.

Credit to https://www.w3.org/Style/Examples/007/units.en.html


## px or pixels

A pixel is the smallest unit of a digital image or graphic that can be displayed and represented on a digital display device.  

## REM

REM (“root em”) in CSS is the font size of the root element of the document.  REM has ability to scale type across the entire page easily.  When specified on the font-size property of the root element, the rem units refer to the property’s initial value.

> REM has ability to scale type across the entire page easily. REM helps you achieve a harmonious and balanced design.  

This means that `1rem` equals the font size of the html element (which for most browsers has a default value of 16px).

Tachyons features a spacing scale based on powers of two that starts at .125rem (for most devices this will be the equivalent of 2px).

- `.125rem` = 2 pixels
- `.25rem`  = 4 px
- `.5rem`   = 8px
- `1rem`    = 16px
- `2rem`    = 32px


## Referencing Tachyons CSS on a web page

Getting started with Tachyons is as simple as adding a link in your webpage to a **.css** file located on content delivery network (cdn), like unpkg.com.

```
<!DOCTYPE html>
<html lang="en">
  <title> </title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="https://unpkg.com/tachyons/css/tachyons.min.css">
  <body>

  </body>
</html>
```

# Common Tachyons Used in our Profile Page

Here's a quick guide to some of the css classes we'll use for our profile web page.

## Borders

You can target any side to put a border on ie. top, right, bottom, left, all.

### `ba` - BORDER ALL

```
.ba {
   border-style: solid;
}
```

### `bb` - BORDER BOTTOM

```
.bb {
   border-bottom-style: solid;
   border-bottom-width: 1px;
}
```

### `bw1` - BORDER WIDTH 1

1st step in scale - .125rem = 2 pixels (.125 * 16 px)

```
.bw1 {
   border-width: .125rem;
}
```

## BORDER RADIUS

There is a four step scale for border radius in addition to a utility that sets border radius to 100%, which when combined with an explicit height and width will produce a circle.

Modifiers:

- 0    = 0/none
- 1    = 1st step in scale
- 2    = 2nd step in scale
- 3    = 3rd step in scale
- 4    = 4th step in scale

### br3 - BORDER RADIUS 3

3rd step in scale

```
.br3 {
   border-radius: .5rem;
}
```
### br-100

Combine `br-100` with a fixed height and width (ex: `h4`, `w4`) to make a circle.

## SPACING

Spacing comes in two flavors. Depending on borders and background colors, the difference between padding and margin can be invisible to the naked eye of the user.

### ma0 - MARGIN ALL - No margin

```
.ma0 {
   margin: 0;
}
```

### ma3 - MARGIN ALL 3

3rd step in scale - 1rem = 16 pixels (1 * 16 px)

```
.ma3  {
 margin: 1rem;
}
```

### mb0 - MARGIN BOTTOM 0

```
.mb0 {
   margin-bottom: 0;
}
```

### mb1 - MARGIN BOTTOM 1

1st step in scale  - .25 rem = 4 pixels (.25 * 16 px)

```
.mb1 {
   margin-bottom: .25rem;
}
```

### mb4 MARGIN BOTTOM 4

4th step in scale - 2rem = 32 pixels (2 * 16 px)

```
.mb4 {
   margin-bottom: 2rem;
}
```

### mt2 - MARGIN TOP 2

2nd step in scale - .5rem = 8 pixels (.5 * 16 px)
```
.mt2 {
   margin-top: .5rem;
}
```

### mv2 - MARGIN VERTICAL 2

2nd step in scale - .5rem = 8 pixels (.5 * 16)

```
.mv2 {
   margin-top: .5rem;
   margin-bottom: .5rem;
}
```

### pb2 - PADDING BOTTOM 2

2nd step in scale -  .5rem = 8 pixels (.5 * 16px)

```
.pb2 {
  padding-bottom: .5rem;
}
```

### ph3 - PADDING HORIZONTAL 3

3rd step in scale

```
.ph3 {
   padding-left: 1rem;
   padding-right: 1rem;
}
```

### pl0 - PADDING LEFT 0

```
.pl0 {
   padding-left: 0;
}
```

### pt5 - PADDING TOP 5

5th step in scale

```
.pt5 {
   padding-top: 4rem;
}
```

## TEXT

Designing for readability across infinite screen-sizes often times requires setting elements to have different text-alignments across breakpoints.
These are simple utilities for setting text-alignment to the left, right, or center of an element.

## tc - text center

text aligned to the center.

```
.tc {
   text-align: center;
}
```

## FONTS

## FONT WEIGHT
The font-weight property sets the weight, or thickness, of a font and is dependent either on available font faces within a font family or weights defined by the browser.

Varying the font-weight of different pieces of text can help create contrast between pieces of information. It can help call attention to a piece of content, or help to make a smaller font-size a bit more readable.

Tachyons provide single purpose classes to set the font-weight of any element at any breakpoint.  http://tachyons.io/docs/typography/font-weight/


## FONT SIZE
A modular scale, like a musical scale, is a prearranged set of harmonious proportions.


### f6 - FONT SIZE 6  

6th (smallest) step in scale which is the smallest in the scale.  .875rem (14px)

```
{
   font-size: .875rem;
}
```

### fw2 - FONT WEIGHT 2

FONT WEIGHT, 2nd step in scale

```
.fw2 {
   font-weight: 200;
}
```

### fw3 - FONT WEIGHT 3

3rd step in scale

```
.fw3 {
   font-weight: 300;
}
```

### i - Font Style Italic

Single purpose classes to set the font-style of any element at any breakpoint.
Italics can be used to emphasize a piece of content. Some common uses of italics include: titles, vehicle names, letters of the alphabet, scientific terms, and quotes.

```
.i {
   font-style: italic;
}
```
## HEIGHTS and WIDTHS

The heights module contains both a five-step height scale based on powers of two as well as a series of percentage values.

The widths module contains both a five-step width scale based on powers of two as well as a series of percentage values

### h5 - Height 5

5th step in height scale

### w5 -Width 5

5th step in width scale

```
.w5 {
   width: 16rem;
}
```

## COLORS / SKINS

### b--light-gray - BORDER COLOR Light gray

Border color, light gray

```
.b--light-gray {
   border-color: #eee;
}
```

[Home](/)
