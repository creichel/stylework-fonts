# Stylework
The Stylework is a rapid styling framework in SCSS and with bourbon.io to create and style websites more rapidly by using standardized basic elements for good usability.

# This repo
This repo is the fonts folder for the whole stylework framework (I'm working on at the moment). It contains free to use fonts with a better folder and naming structure.

# Usage

At the moment I'm using this repo with a big amount of files. I'm creating a `.scss`-file for every single font that contains more information about the font, like which font face should be used for bold, regular, lighter, italic etc. fonts. Then I have another file called `fonts.scss` which imports the  `.scss`-files which I want to use in this project. So I have two files:

- `_fonts.scss`
- `_[ENTER FONT NAME HERE].scss`

## `_fonts.scss`
The content of `_fonts.scss` is the following:

```
$font-path: "[THE PATH TO THE FONTS FROM THIS REPO]";

@import "fonts/fontawesome";
@import "fonts/fira_sans";
@import "fonts/lora";
@import "fonts/merriweather";
@import "fonts/computer_modern_serif";
@import "fonts/computer_modern_concrete";
@import "fonts/open-sans";

.
.
.
```

Et cetera. For icon fonts it contains also some little styling informations:

```
%icon-fonts {
  display: inline-block;
  speak: none;
  font-style: normal;
  font-weight: normal;
  font-variant: normal;
  text-transform: none;
  line-height: 1;
  @include font-smoothing;
}

.icon {
  @extend %icon-fonts;
  font-family: FontAwesome;
}

.no-icon {
  &:before {
    display: none !important;
  }
}
```

## `_[ENTER FONT NAME HERE].scss`
This is interesting now. Thanks to bourbon.io I simply have to insert following for Open Sans font face, for example:

```
@include font-face(Open Sans, '#{$font-path}/Open_Sans/light/font', lighter);
@include font-face(Open Sans, '#{$font-path}/Open_Sans/light/italic/font', lighter, italic);
@include font-face(Open Sans, '#{$font-path}/Open_Sans/semibold/font', bold);
@include font-face(Open Sans, '#{$font-path}/Open_Sans/semibold/italic/font', bold, italic);
@include font-face(Open Sans, '#{$font-path}/Open_Sans/regular/font', normal);
@include font-face(Open Sans, '#{$font-path}/Open_Sans/regular/italic/font', normal,italic);
```

That's it. I also can optimize the performance of my site by simply commenting out the fonts I don't use.

# Yea, but why?
Maybe you're asking why I'm using this more complex and more crazy way to import all fonts in a project to just use a few. Or why I'm using a `.scss`-file for every single font. 

As long as I'm developing some web projects as an indie-developer I'm thinking about the optimal workflow by questioning hundreds of thousands of questions. How and when do you switch from designing with Photoshop, Illustrator or Sketch to the developing part? When is it optimal, when too early, when too late? What do you need to develop a project?

This is about styling and trying out new things directly in the code. This font directory is structured with a readable path structure by using `[FONT NAME]/regular/font` for example. It has to be easy to add a new font - and understand how to choose it.

# Attention
I'm still thinking about the optimal structure. So this idea isn't finished at all but I'm using it for years now.
