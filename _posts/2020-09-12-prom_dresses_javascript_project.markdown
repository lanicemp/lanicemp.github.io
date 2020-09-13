---
layout: post
title:      "Prom Dresses JavaScript Project"
date:       2020-09-13 03:21:27 +0000
permalink:  prom_dresses_javascript_project
---



When working on my JavaScript project I had to meet different objectives.  They were to create a JavaScript front end that pulls information from a Ruby on Rails backend.   At first this project can be intimidating but as you come to realize with practice it does get easier and what once was intimidating is now achievable.  

To begin this project I first created a Ruby on Rails API that was connected to a PostgreSQL database.  I initially had a problem connecting my windows system to the  a PostgreSQL database and I addressed that issue in my previous blog post https://lanicemp.github.io/how_i_overcame_my_postgresql_connection_and_role_error.  Once my system was connected to the database I began to create my backend.     Below is a list of commands that were used to create my backend 


```
mkdir DressApp
rails new prom_dresses-api --api --database=postgresql
rails g scaffold dress name:string  silhouette:string  neckline:string length:string color:string img_url:string price:integer dress_id:integer 
rails db:create 
rails db:migrate
*add gems 'pry', gem 'faker', and uncomment rack cors, gem 'fast_jsonapi' 
bundle install 
*in config initializers cors uncomment the code and change the word example to a * to allow all locations
```

With the commands above I was successfully  able to create my main file for this application that would contain my prom_dress-api directory with the PostgreSQL database.  I also created my table for my dress and its attributes.   I also added some gems that would help with the process, as will as updated my cors file to allow different locations.  

Once this was built out I updated my dress controller to render JSON.  This allows for the information in the table to be able to populate by calling a URL. Then I am able to view the information in my database on my screen.  I made sure to add seed data so that I can be sure this step was working.  

NEXT STEPS: JavaScript Frontend

Building out my JavaScript frontend When building out by JavaScript frontend I have to first make sure that I was back in my main directory DressApp then I created  the following files using the steps below. 

```
mkdir Dress-js-frontend
touch index.html
mkdir bin src styles
cd src 
mkdir adapters components
touch index.js 
cd adapters
touch DressesAdapter.js
cd .. 
cd components
touch app.js dress.js dresses.js
cd ..
cd .. 
cd styles 
touch style.css 
```

When all of these files were created I began to code into the index.html file to make sure that it was able to open up and display text.  I used the extension live server to be able to open my server.  

I also made sure that I connected the script for the different files to the index.html page so that It will  run all necessary files to operate properly.  The script that I used is listed below.  

```
<script type="text/javascript" src="src/components/dress.js"></script>
  <script src="src/components/dresses.js"></script>
  <script src="src/components/app.js"></script>
  <!-- <script src="src/adapters/DressesAdapter.js"></script> -->
  <script src="src/index.js"></script>
```

Working on this application had its challenges and definitely pushed my understanding of JavaScript as well.  I feel much more confident with the use of event listeners, getting elements by id , and also a better understanding of scope.  
I understand the creating and populating of the json as html on the page.  I struggled with getting the json to render automatically when working with different databases.  As well as creating functions for special features and where those functions are to be placed to make sure that they are called properly.  

Overall I am excited about what I was able to create and look forward to making another application.  

