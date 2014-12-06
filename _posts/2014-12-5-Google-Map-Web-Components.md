---
layout: post
title: Google Map Web Components
---

### 1. Google SpreadSheets:
  Firstly, you have to create a Google SpreadSheet file. You can store any data that you want as long as it has longtitudes and latitudes available for google maps.
  
 This is the spreadsheet example that I use for this project:
 [Speadsheeet Example](https://docs.google.com/spreadsheets/d/1AsR71hx_Kw_Yq--UEEq3mWxzk73RYsdqZTMxBjJrJjg/edit?usp=sharing)

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
  - It will ask you some questions to help you buil the bower.json file
  - Install Polymer
  ```
      bower install polymer --save
  ```
  It will add the dependencies object in bower.json and create the bower_components folder which contain polymer and platform for you ready to use.
