---
title: "University of Bordeaux theme"
subtitle: "The unofficial theme"
author: "Laurent Bergé"
date: "2022-09-09"
institute: "University of Bordeaux, B<sub>x</sub>SE"
output:
  xaringan::moon_reader:
    chakra: libs/remark-latest.min.js
    css: "ub_theme.css"
    includes:
      after_body: "ub_theme.html"
    self_contained: true
    nature:
      highlightStyle: magula
      highlightLines: true
      countIncrementalSlides: false
---




# Introduction

Welcome to this introduction to the *unofficial* University of Bordeaux theme.

First, to use it, you need the following lines in your YAML:
```{}
css: "path_to/ub_theme.css"
includes:
  after_body: "path_to/ub_theme.html"
```

You can find these files on the [dedicated Github page](https://github.com/lrberge/ub_theme/).

--

This theme is a combination of CSS and javascript (.color2[actually it's mostly javascript]).

---

# Dedicated theme colors

There are three main colors:

 - the main theme is blue: .bg-color-192E5B.w-30px.h-30px[&nbsp;]
 - the first paired color is pink: .bg-color-F94060.w-30px.h-30px[&nbsp;]
 - the second paired color is (.color2[kinda]) gold: .bg-color-9E911B.w-30px.h-30px[&nbsp;]

--

.h-1em[]

You can summon the first pair with `color1`, `it1`, `bold1` and `strong1`.

 - I use it mostly for .bold1[highlighting]

--

.h-1em[]

You can summon the second pair with `color2`, `it2`, `bold2` and `strong2`.

 - I use it mostly for commenting (.color2[like here]).footnote[{altstar}I use a desaturated color for comments so that comments are easy to visually ignore when focusing on the main text.]

---

Did you notice where the text is?

---

# Default text height

The text is, by default, at 70% of the slide height.

Note that when there is a lot of content (.color2[like in the next slide]), the content is then vertically centered.

---

Illustration that the text

.h-400px[
![](lord_rings.jpg)
]

is vertically centered.

---

class: fs-17px

# Blocks

You can add blocks using `.block[Text]`.

.block[Blocks are simple boxes.]

--

To add a title to the box, place it right at the beginning in curly braces: <br/>
`.block[{Title} Text]`.footnote[{altstar} I agree it's pure Beamer nostalgia.]

.block[{Block pun} Who doesn't like block and roll?]

--

Additionally, you have the `.theorem` and `.definition` environments .comment[they don't accept titles].

.definition[
Recursivity: Create this with `.definition[Recursivity: Create this with ...]`
]

---

# Footers

Add a footer with `.footer[text]`. .footer[That's a footer created with `.footer[text]`.]

--

You can use `.foootnote[text]` to add.footnote[This should be footnote 1.] auto-incremented footnotes..footnote[This should be footnote 2.]

--

To have non-numbered footnotes, you can add a symbol in curly braces: <br/>
`.footnote[{symbol} text]`.footnote[{note}Note that .comment[for complicated reasons] maths don't work well or is cumbersome in footnotes. ]

--

The commands .color1[star].footnote[{star}the `star` footnote.] and .color1[altstar].footnote[{altstar}the `altstar` footnote.] insert unicode stars as symbols. <br/> Use them with `.footnote[{star} text]`.

---

# Source

.source[Usually the link to the source.]

A last environment connected to footers is the .color1[source].

`.source[text]` is equivalent to `.footer[*Source*: text]`

---

# Columns

You can create columns with the `.leftcol` and `.righcol` environments.

.bg-color-mediumTurquoise.leftcol[By default, their widths]
.right.bg-color-indianred.rightcol[are 50-50.]

--

.h-2em[]

Use `.leftcol-width` to give a custom width to the left column. The right column is .color1[automatically adjusted].

Example with `.leftcol-25[text]`.footnote[{altstar}The unit is the percentage.]

.bg-color-mediumTurquoise.leftcol-25[Now the left is 25%,]
.right.bg-color-indianred.rightcol[and the right is 75%.]

---

# 3+ columns

You can add more than two columns with the `.column-size` environment.

.column-20.bg-color-linen.ta-center[Small column <br> `.column-20`]

.column-60.bg-color-lavender.ta-center[Large column <br> `.column-60`]

.column-20.bg-color-linen.ta-center[Small column <br> `.column-20`]

--

As you can notice, in this environment the total width is extended. The reason is that when I use multiple columns, I usually want enough space for each column, which requires extra space on each side. 

You can easily change that behavior with the `margin` property of the `.column-container` class in the CSS file.

---

# Panels

.panelset[

.pane[{Creation}

To create a panel, use:
```{}
.panelset[

.pane[{Creation}

To create a panel, use...

]

]
```

]

.pane[{Details}

You create a pane with the syntax `.pane[{title} content]`. 

Note that the title must be present.

]

.pane[{Limitations}

These panels do the job but are limited in terms of customization.

For much more detailed panels, please have a look at [Garrick Aden-Buie](https://www.garrickadenbuie.com/)'s [xaringanExtra's panelset](https://pkg.garrickadenbuie.com/xaringanExtra/#/panelset).

]


]


---

# Images

Images are automatically adjusted in height so that they don't overflow vertically..footnote[{altstar} It's very common to have images that are not as wide as the 16:9 ratio, and these images do overflow vertically when inserted. This was a major source of frustration when I started using Xaringan, and of course adjusting the height manually for each image was definitely a no go. That's the main reason I started developing this theme. <br/> &nbsp;]

![](lord_rings.jpg)


---

# Images: Custom sizes

Anticipating the next slide, you can set custom heights and width with the syntax `.h-size[stuff]` and `.w-size[stuff]`. The default unit is the percentage.

--

To set the height of the figure below to 200px, I just used: <br/>`.h-200px[![](path.jpg)]`


.h-200px[![](lord_rings.jpg)]


---

# CSS

You can set up .comment[a few] custom CSS environments very easily. 

--

Use `.color-colorName` to create an environment with the appropriate color. <br/> .color-IndianRed[This sentence has been created with `.color-IndianRed`.] <br/> .color-006400[This one with `.color-191970`.].footnote[The color name must be either an [HTML color name](https://www.w3schools.com/colors/colors_names.asp) or a hex code. Note that color names are .color1[case insensitive] and are .color1[partially matched].]

--

Use `bg-color-colorName` to .bg-color-teal[change the background color.]

--

Use `fs-size` to .fs-30[change].footnote[{2a}`.fs-30[change]`, the default unit is the pixel.] .fs-12[the] .fs-2rem[font size].footnote[{2b}`.fs-2rem[font size]`, any other valid size work.].

--

As seen previously, use `.h-size` and `.w-size` to set to a custom height/width..footnote[{3} The default unit is the percentage.]


---

# Vertical spacing

Use empty `.h-size` environments to easily create vertical space. 

--

### Example


With `.h-25[]`

.h-25[]

I end up here and with `.h-2em[]`

.h-2em[]

I end up there.


---

# The text in the header does not overflow thanks to auto-shrinking capabilities

You can use `.auto-fit` to enforce a piece of text to fit the total text-width:

.auto-fit[That's a large text.]

--

You can also use `.auto-shrink` but then only oversized text is fit to the text width. Actually I only use this for headers .comment[like in this slide].


---

class: section

# Limitations


---

# Section

The previous slide was created with `class: section`.

---

# Limitations

.block[{Title slide}

- the title slide is not made for paper presentations but for teaching

- there's no way to have multiple authors in a nice way

- the layout is problematic for long titles

]


???

Todo: 
 - the columns environment
 - the panelset










