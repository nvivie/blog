---
layout: post
title: CSS Pre-processors
---

I started to hear about CSS Preprocessors few months ago, the most popular one that I know so far are SASS, LESS, Compass.
The concept fascinates me: CSS files that could contain variables, functions,math functions, nesting, and other features. After development, these special files will be compiled into regular CSS files that all web browsers could understand. Personally, I have been working with CSS (including my own css and someone else's css files) for almost 2 years. One bad thing that I shoudn't have done: Retyping the same thing too many times to apply the similar styling to seperate elements. With CSS preprocessors, it helps me define global styles with functions and then re-use them throughout my css where I need them.

The fact that CSS preprocessors allow you to use variables, mixins and functions is pretty handy. By using these features, you can define a value or a group of values once at the beginning of your stylesheet file. It becomes much easier to make changes later.
For example:

{% highlight css %}
$text-color: #222223;
$light-blue: #a7eaf6;
$std-padding: 20px;

header{
  background:$light-blue;
}

h2{
  color: @text-color;
  background:$light-blue;
  padding: $std-padding *2; // 40px
}

{% endhighlight %}

In addition, CSS Preprocessors support nesting. This is one of my favorite feature, it keeps things so organized and it makes sense. For example, instead of using:

{% highlight css %}
.front {
  -webkit-transition: all 0.3s ease;
  transition: all 0.3s ease;
}

.front:hover {
  -webkit-filter: hue-rotate(90deg);
  -moz-filter: hue-rotate(90deg);
  filter: hue-rotate(90deg);
}

{% endhighlight %}

You could use:

{% highlight css %}
.front {
  -webkit-transition: all 0.3s ease;
  transition: all 0.3s ease;
  
  &:hover {
  -webkit-filter: hue-rotate(90deg);
  -moz-filter: hue-rotate(90deg);
  filter: hue-rotate(90deg);
  }
}

{% endhighlight %}

Lastly, CSS Preproccessors are easy to set up. By adding another step to your development workflow, you save a lot of time of not reapeating yourself and keep you code under control. With Sass, a simply command line will tell Sass to watch your sass files, then recompiling automatically every time you save changes. One more nice thing about CSS preprocessor is that can tell you the errors while CSS can't.


You can check the example below:
{% highlight css %}
$std-pad: 20px;
$std-duration: 0.3s;

@mixin transition($values...){
  -webkit-transition: $values;
  transition: $values;
}

@mixin transform-style($values...){
  -webkit-transform-style: $values;
  -moz-transform-style: $values;
  transform-style: $values;
}

@mixin transform($values...){
  -webkit-transform: $values;
  -moz-transform: $values;
  transform: $values;
}

@mixin filter($param){
  -webkit-filter: $param;
  -moz-filter: $param;
  filter: $param;
}

@mixin backface-visibility{
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}
@mixin perspective{
  -webkit-perspective: 800px;
  perspective: 800px;
}

//----------------CSS --------------------//

.container {
  position: relative;
  width: 620px;
  height: 400px;
  border: 1px dotted #333;
  padding: $std-pad;
  margin: $std-pad auto;
  @include perspective;

  &:after{
  clear: both;
  display: table;
  content: '';
  }
}


.card {
  float: left;
  width: 300px;
  height: 400px;
  position: relative;
  @include transform-style(preserve-3d);

  /* DON'T WORRY ABOUT/ALTER THE TWO RULES BELOW! */
  @include transition(transform 0.7s ease-out);

  .card1 {
  margin-right: $std-pad;
  }
}


.face {
  display: block;
  position: absolute;
  width: 100%;
  height: 100%;
  @include backface-visibility;
}

.front {
  @include transition(all $std-duration ease);
  &:hover{
      @include filter(hue-rotate(90deg));
  }
}



.back {
  @include transform(rotate3d(0, 1, 0, 180deg));
  @include transition(all $std-duration ease);

  &:hover{
     @include filter(grayscale(70%));
  }
}



.card.flipped {
  @include transform(rotate3d(0, 1, 0, 180deg));
}

#flipper {
  display: block;
  margin: $std-pad auto;
  font-size: 24px;
}

{% endhighlight %}
