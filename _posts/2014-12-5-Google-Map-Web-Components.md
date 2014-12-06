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
  
### index.html
In your index file, first thing you have to do is to load the platform in your bower_components folder. This platform is a layer of polyfill that support web components for all browsers. Insert this script tag in the header

```
<script type="text/javascript" src="bower_components/platform/platform.js"></script>
```

Use the link tag to import polymer.html

```
<link rel="import" href="bower_components/polymer/polymer.html">
```

### Install google map components
In your command line, get to your project by

```
cd my-project
```
Install Google Web Componenents

```
bower install google
