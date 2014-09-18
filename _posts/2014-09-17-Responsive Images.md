---
layout: post
title: Reponsive Images
---

### The need of responsive images

Images are some of the most important pieces of information on the web. It’s always tricky to try to fit only one image to all devices screen sizes (i.e computers, tablets, mobiles…). “Responsive images ” is a set of technique that allows webpages to serve the needs of both mobiles and desktop users. Images will display at their dimension as long as there is enough room in the html container to do so. “Responsive images ” is a big help for the device performance as well. Users will not have to deal with loading  big high-resolution  images and waiting forever when they only browse on their mobiles and vice versa. To solve the problems, we’ll want our images to be available in multiple resolutions and sizes so that they scale efficiently.

### Why using them can be so difficult

Responsive images aim to adapt a website so it works optimally within known environmental constraints. Keep in mind that developers have to deal with display dimensions  from desktop to mobile sizes and display quality such as pixel density, colour capacity. The goal is to provide the best clarity of content, ease of use, load times, and device performance for any given user. Practically this means we give consideration to each constraint and in response changes the design by adjusting some aspect of it. For example:
⋅⋅*Adjusting multi-column layouts to single columns to avoid columns that are too narrow
⋅⋅*Changing font sizes to maintain readability on different screens
⋅⋅*Loading smaller images for devices that do not require large images

 “Retina images” are also a challenge because if you have sized your layout with ems or percentages, then you can not be sure of the exact pixel dimensions of each image being displayed.


### How to implement responsive images
#### By using CSS
````
//mobile first
.banner {
      height: 200px;
      background-image: url('banner-mobile.jpg');
      background-repeat: no-repeat;
      background-size: cover;
      text-align: center;
   font-size: 5rem;
   }
// high res Mobile 
@media (-webkit-min-device-pixel-ratio: 2), (min-resolution: 192dpi) {
    .banner {
      background-image: url('banner-mobile@2x.jpg');    
    }
  }
````
````
//tablet
@media(min-width: 768px){
      .banner{
        background-image: url('banner-tablet.jpg');
        height: 300px;
        font-size: 7rem;
      }
//high res tablet
  @media (-webkit-min-device-pixel-ratio: 2) and (min-width: 768px),
    (min-resolution: 192dpi) and (min-width: 768px) {
      .banner {
        background-image: url('banner-tablet@2x.jpg');
      }
    }
````

````
//desktop
@media(min-width: 1024px){
      .banner{
        background-image: url('banner-desktop.jpg');
        height: 400px;
        font-size: 9rem;
      }
     // high res desktop
@media (-webkit-min-device-pixel-ratio: 2) and (min-width: 768px),
    (min-resolution: 192dpi) and (min-width: 768px) {
      .banner {
        background-image: url('banner-tablet@2x.jpg');
      }
````

<!--{% endhighlight %}-->
