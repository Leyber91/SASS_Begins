# SASS_Begins
Beginning with SASS

## INTRODUCTION

This repository is crested to initialize you in SASS, for this purpose first we will answer some questions in order to have a deeper insight of what SASSis about.


**What is SASS? What does SASS stand for?**
+ Sass (short for syntactically awesome style sheets) is a preprocessor scripting language that is interpreted or compiled into Cascading Style Sheets (CSS).
+ Sass allows variables to be defined. Variables begin with a dollar sign ($). Variable assignment is done with a colon (:).



**What is a CSS pre-processor?**
+ A CSS preprocessor is a program that lets you generate CSS from the preprocessor's own unique syntax. There are many CSS preprocessors to choose from, however most CSS preprocessors will add some features that don't exist in pure CSS, such as mixin, nesting selector, inheritance selector, and so on.


**What does a pre-processor have to do with SASS?**
+ In short, Sass is a CSS preprocessor, which adds special features such as variables, nested rules and mixins (sometimes referred to as syntactic sugar) into regular CSS. The aim is to make the coding process simpler and more efficient.


**Why use SASS?**
+ "Do you really have to use Sass?" For the most part, no you don't need Sass to get work done. The internet has been around for a long time and CSS was here WAY before Sass and people were able to get work done.

**SASS has disadvantages? Which are?**
+ The developer must have enough time to learn new features present in this preprocessor before using it.
+ Using Sass may cause losing benefits of browser's built-in element inspector.
+ Code has to be compiled.
+ Difficult Troubleshooting.

**What is a SASS Variable? Explain why are useful**
+ Sass variables are simple: you assign a value to a name that begins with $ , and then you can refer to that name instead of the value itself. ... Unlike a property, which can only be declared in a style rule or at-rule, variables can be declared anywhere you want. To use a variable, just include it in a value.

**Explain the SASS variables property with an example.**
+ A variable declaration looks a lot like a property declaration: it’s written <variable>: <expression>. Unlike a property, which can only be declared in a style rule or at-rule, variables can be declared anywhere you want. To use a variable, just include it in a value.

```` scss
$base-color: #c6538c
$border-dark: rgba($base-color, 0.88)

.alert
  border: 1px solid $border-dark

````


**What is a mixin? Why is it important? Give an example**

+ In object-oriented programming languages, a mixin is a class that contains methods for use by other classes without having to be the parent class of those other classes. How those other classes gain access to the mixin's methods depends on the language.
+ Mixins allow you to define styles that can be re-used throughout your stylesheet. They make it easy to avoid using non-semantic classes like . ... A mixin's name can be any Sass identifier, and it can contain any statement other than top-level statements.

```` scss
@mixin important-text {
  color: red;
  font-size: 25px;
  font-weight: bold;
  border: 1px solid blue;
}

.danger {
  @include important-text;
  background-color: green;
}

````


**What is SCSS? Give an example**
+ The newer syntax, "SCSS" (Sassy CSS), uses block formatting like that of CSS. It uses braces to denote code blocks and semicolons to separate rules within a block. 
+ The indented syntax and SCSS files are traditionally given the extensions . sass and . scss, respectively.
```scss
$theme-1: (
   container: (
       bg: #e4ada7,
       color: #000,
       border-color: #000
   ),
   left: (
       bg: #d88880,
       color: #fff,
       height: 100%,
       width: 69%
   ),
   right: (
       bg: #cc6359,
       color: #fff,
       height: 100%,
       width: 29%
   ),
   button: (
       bg: #481b16,
       color: #fff
   )
);

```

If we wanted to access each section of our scheme theme-1 and its sub-maps, we use the @each directive to loop through each of them:

```scss
@each $section, $map in $theme-1

```


**What is the difference between .scss and .sass syntax.**

+ SASS (Syntactically Awesome Style Sheets) is a pre-processor scripting language that will be compiled or interpreted into CSS. 
+ SassScript is itself a scripting language whereas SCSS is the main syntax for the SASS which builds on top of the existing CSS syntax.

**SCSS**

````scss
/* .scss file */ 
$bgcolor: blue; 
$textcolor: red; 
$fontsize: 25px; 
  
/* Use the variables */ 
body { 
  background-color: $bgcolor; 
  color: $textcolor; 
  font-size: $fontsize; 
} 
````
**SASS**
````scss
/* SASS */ 
  
$primary-color: green 
$primary-bg: red 
  
body  
  color: $primary-color 
  background: $primary-bg 
````


**In which cases would we use SCSS? And in which cases would we use SASS?**

Cases to use SASS:
+ SASS is used when we need a original syntax, code syntax is not required for SCSS
+ SASS it is used widely in many different companies
+ Used for any operating system platform

Cases to use SCSS:
+ It is sued when there is no requirement or criteria about the code syntax used.
+ Used for cross-platform pperating system.


**Explain how traditional CSS and Preprocessed CSS workflows are different.**
+ CSS preprocessors add functionality to CSS files
+ If you have written in any CSS preprocessing language, then you can convert it into another type of data.


**Can we create functions with SASS? If it is true, give an example.**

+ Functions allow you to define complex operations on SassScript values that you can re-use throughout your stylesheet. They make it easy to abstract out common formulas and behaviors in a readable way.
+ Functions are defined using the @function at-rule, which is written

```` scss
@function invert($color, $amount: 100%) {
  $inverse: change-color($color, $hue: hue($color) + 180);
  @return mix($inverse, $color, $amount);
}

$primary-color: #036;
.header {
  background-color: invert($primary-color, 80%);
}
````


**What is nesting? Is it useful? Give an example of nesting**
+ Nesting is a term used to describe the placement of one or more objects within another object. 
+ For example, when referring to a computer, nesting may refer to inserting a graphic image into a word processor. ... 
+ Nesting isolates the code it contains from code scoped outside the nested section.


**Why use @import?**
+ The Sass team discourages the continued use of the @import rule. Sass will gradually phase it out over the next few years, and eventually remove it from the language entirely. Prefer the @use rule instead.

**How can we import other CSS/SASS files in SASS? Give an example**
+ You can use @use rule for it. This rule loads another Sass file as a module, which means you can refer to its variables, mixins, and functions in your Sass file with a namespace based on the filename. 
+ Using a file will also include the CSS it generates in your compiled output!
+ A stylesheet’s @use rules must come before any rules other than @forward, including style rules. However, you can declare variables before @use rules to use when configuring modules.

````scss
// foundation/_code.scss
code {
  padding: .25em;
  line-height: 0;
}
// foundation/_lists.scss
ul, ol {
  text-align: left;

  & & {
    padding: {
      bottom: 0;
      left: 0;
    }
  }
}
// style.scss
@use 'foundation/code';
@use 'foundation/lists';
````



**Explain the concept of inheritance in SASS.**
+ Sass Inheritance/ Extend. In Sass, @extend is used to share a set of CSS properties from one selector to another. ... The @extend feature of Sass allows classes to share a set of properties with one another. In complicated CSS where many classes are put together, duplication of properties may occurs.
  
````scss
<!-- /* This CSS will print because %message-shared is extended. */ -->
%message-shared {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

<!-- / This CSS won't print because %equal-heights is never extended./ -->
%equal-heights {
  display: flex;
  flex-wrap: wrap;
}

.message {
  @extend %message-shared;
}

.success {
  @extend %message-shared;
  border-color: green;
}

.error {
  @extend %message-shared;
  border-color: red;
}

.warning {
  @extend %message-shared;
  border-color: yellow;
````

**Why use @extend? Give an example**

+ When to use extend
+ Using @extend produces DRY CSS.
+ With @mixin the resulting code isn’t as DRY.

**Mixin example**
````scss
@mixin button {  
  background-color: green;  
}

.button-1 {  
  @include button;  
} 

.button-2 {  
  @include button;  
}

<!--CSS compiles as... -->
.button-1 {  
  background-color: green;  
}

.button-2 {  
  background-color: green;  
}

````

**Extend example**
```` scss
.button {  
  background: green;  
}

.button-1 {  
  @extend .button;  
}

.button-2 {  
  @extend .button;  
}
<!--CSS compiles as... -->

.button, .button-1, .button-2 {  
  background: green;  

````