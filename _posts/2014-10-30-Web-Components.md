---
title: Web Components
layout: post
---
###Part 1:
At first, I have conflicting feelings about Web Components. I am very excited and very nervous.

This is pretty new and different way of adding new features to browsers. With web components, they give developers much more power than they had before. You can extend existing elements by customizing your own custom elements are also just HTML elements. 
Creating your own HTML element seems actually quite easy. The only two requirements are that its name must contain a dash, and its prototype must extend HTMLElement. You can name whatever you want as long as it makes sense to you and it helps your code more readable. I am also very excited about the shadow DOM even though I don't entirely get the whole concept yet.

Since Web Components are the new hotness, I am afraid that it might be a rocky transition to this new way of thinking. Also I have a bad feeling about browser support. Although web components landed in Chrome 36, they only have partial support in Firefox, and they are not here for Safari and IE. It probably is one of the reason that web components are not ready for production.

###Part 2:
I've tried to experiment with these three components Templates, Custom Elements, Shadow DOM, and here are my initial thoughts.

####Templates: 
Templates might solve many performance issues. One of the biggest problems would be images loading. Browsers generally don't care whether <img> is hidden or not, they still load it. For pages with lots of images througout the page, we can priotize and load only the ones that we need to see. By giving a template, we don't have to recreate our content each time. The cool thing is the template can sit anywhere in our html file. To activate this piece of inert code then, we need to clone the template and append it to the DOM.


####Custom Elements:
Custom elements get me the most excited of all the Web Components. We have the power to create expressive and maintainable markup. Basically, custom elements just give us a new tag to use instead of using general <div>. We can create custom elements easily with a little bit Javascript. Now the question that I have in mind is "How do we make our content reachable to search engine? Will they understand my custom elements tags?"

#### Shadow DOM
