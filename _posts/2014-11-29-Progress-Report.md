---
layout: post
title: Progress Report Final Project
---

### Current status on the final project
- Got the Fusion Table Map ID ready to use. I will need to pull out the datas from Goole SpreadSheet.
- Setting up the index.html page to display the google maps.
- Declared the new custom element ( <google-map> ) tags

### The steps remaining to complete the project:
- Keep working on Web Components
- Import and apply Polymer 
- Instructions how to use the google maps web component

### Here it's the benefit by using Polymer's Google Map component.

#### Old way
{%highlight html%}
<style>
  #map-canvas{
  height: 100%;
  width: 100%;}
</style>
<div id="map-canvas"></div>
<script src="https://maps.googleapis.com/maps/api/js?v=3.exp"></script>
<script type="text/javascript">
  var map;
  function init(){
    var mapOptions = {
      zoom:10,
      center:new google.maps.LatLng(41.876438, -87.620576)
    };
    map = new google.maps.Map(document.getElementById('map-canvas'), mapOptions);
  }
  // add DOM listener to the window object, when the map is loaded, it will execute init function
  google.maps.event.addDomListener(window, 'load', init);
</script>

{%endhighlight%}

#### With Polymer's Google Map Component
{%highlight html%}
<style>
  #map-canvas{
  display: block;
  height: 100%;}
</style>
<google-map latitude="41.876438" longtitude="-87.620576" zoom="10"><google-map>
{%endhighlight%}
