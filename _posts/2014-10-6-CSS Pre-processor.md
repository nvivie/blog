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
<p data-height="680" data-theme-id="0" data-slug-hash="ekpoH" data-default-tab="result" data-user="nvivie" class='codepen'>See the Pen <a href='http://codepen.io/nvivie/pen/ekpoH/'>ekpoH</a> by Vi (<a href='http://codepen.io/nvivie'>@nvivie</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>
