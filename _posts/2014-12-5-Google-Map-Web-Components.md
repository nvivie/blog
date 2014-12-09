---
layout: post
title: Google Map Web Components
---

This is my example of using Web Components + Polymer + Google SpreadSheets + Google Maps

[Public Art Projects in Chicago](http://iam.colum.edu/students/vi.nguyenngocuyen/FA2014/Emergent%20Web%20Technologies/app/index.html)

### 1. Google Map powered by Google SpreadSheets:
  Firstly, you have to create a Google SpreadSheet file. You can store any data that you want as long as it has longtitudes and latitudes available for google maps. These are the datas that will run on google map marker objects.
  
 This is the spreadsheet example that I use for this project:
 [Speadsheeet Example](https://docs.google.com/spreadsheets/d/1AsR71hx_Kw_Yq--UEEq3mWxzk73RYsdqZTMxBjJrJjg/edit?usp=sharing)
 
 
 Once you create your google speadsheet file, you will be able to find your key ID of your google spreadsheet in the URL bar (https://docs.google.com/spreadsheets/d/```1AsR71hx_Kw_Yq--UEEq3mWxzk73RYsdqZTMxBjJrJjg```/edit#gid=0)

<strong>Key: 1AsR71hx_Kw_Yq--UEEq3mWxzk73RYsdqZTMxBjJrJjg </strong>
 

### 2. Install Bower and Polymer

#### Install Bower:
  Bower is a package manager for the web.
  
  - Download and install Node.js from nodejs.org
  - Use command line to install Bower: 
  
  ```
      npm install -g bower (-g: to make Bower globally available in the system )
  ```
  
  - Create new folder that runs Bower : 
  
  ```
      mkdir my-project
  ```
  
  - Run bower inside my-project
  
  ```
      bower init
  ```
  
  - It will ask you some questions to help you build the bower.json file
  
  - Install Polymer
  
  ```
      bower install polymer --save
  ```
  
  It will add the dependencies object in bower.json and create the bower_components folder which contains polymer and platform for you ready to use.
  
  So right now, in your my-project folder, you have bower_components and bower.json. You can create your index.html file ready to test.
  
### 3.index.html
In your index file, first thing you have to do is to load the platform in your bower_components folder. This platform is a layer of polyfill that support web components for all browsers. Insert this script tag in the header

```
<script type="text/javascript" src="bower_components/platform/platform.js"></script>
```

Use the link tag to import polymer.html

```
<link rel="import" href="bower_components/polymer/polymer.html">
```

### 4.Install google map components
In your command line, get to your project by

```
cd my-project
```

Install Google Web Componenents

```
bower install GoogleWebComponents/google-map
```

You will find google-map folder installed in bower_components folder. You just need to import google-map.html file in the header

```
<link rel="import" href="bower_components/google-map/google-map.html">
```
For the other Google Web Componenents, you do the same step as example above by using ``` bower install ```

Check this website for available google web components: 
[Google Web Components](http://googlewebcomponents.github.io/)


### 5.Polymer and Google Web Componenents
Now you have your dependencies installed.
Create your custom element in seperate html file. Don't forget to inset an import link in your index.html.

```
&lt;polymer-element name="my-element"&lt;
  &lt;template&lt;&lt;google-sheets key="1AsR71hx_Kw_Yq--UEEq3mWxzk73RYsdqZTMxBjJrJjg" rows="{{rows}}" published&lt;&lt;/google-sheets&lt;
      &lt;google-map fittomarkers id="google_map"&lt;
        &lt;template repeat="{{row in rows}}"&lt;
          &lt;google-map-marker latitude="{{row.gsx$lat.$t}}" longitude="{{row.gsx$lng.$t}}"&lt;&lt;/google-map-marker&lt;
        &lt;/template&lt;
      &lt;/google-map&lt;&lt;/template&lt;
&lt;/polymer-element&lt;

```

Inside this google template, you have google-sheet components which are the one will talk to your spreadsheet. 

```
key="1AsR71hx_Kw_Yq--UEEq3mWxzk73RYsdqZTMxBjJrJjg" 
```
is the key of your google spreadsheet. Your data will be called in your ```rows``` attribute. Make sure your spreadsheet is published (in spreadsheet, go to file --> publish to the web).

In the ```google-map```, you declare the template, looping over the data that you pull out from spreadsheet and stamping out the google map marker childrens.

The last thing you have to do is to declare the ```my-element``` tags in your index.html

### 6.Tips: Web Components don't run locally
You can run it in local web server like Python server.
In your command line:
```
python -m SimpleHTTPServer
```
