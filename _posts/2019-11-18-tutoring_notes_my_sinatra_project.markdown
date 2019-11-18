---
layout: post
title:      "Tutoring Notes My Sinatra Project "
date:       2019-11-18 18:42:27 -0500
permalink:  tutoring_notes_my_sinatra_project
---


My Sinatra project was difficult for me to start.  One thing that I found helpful was the use of Corneal gem.  This gem definetely gave me a foundation of how to be able to start developing.  I found this gem useful because it gave me the foundation to generating the model, controller and views with a scaffold also called the MVC.   The scaffold has the MVC inside of the app .  Where the controller leads to ttwo files the application_controller.rb and the new_model_controller.rb.The Models leads to one file the new_model.rb. Lastly the views leads to the new models folder, layout.erb file, and welcome.erb file.  The new models folder has four files of index, show, new, and edit.html.erb inside of them.  

From this base I was able to develop multiple controllers for my tutoring notes application.  The sessions_controller that controls the login process and the users session.  The application controller that has my helper methods that work mostly with my sessions controller and controls the application.  My student user controller that has the parameters for the student and verifys the passowrd.  My questions controller that controls the questions that are asked and leads to the main views of he applicatoin after the login process.  Lastly my answers_controller that controls the answers and comments for each individual instance of a question.  

The controller that I felt took the most work was my questions controller.  Within this controller I had my first direction which was /questions.  This method checks if the user is logged in and if there are currently any questions that need to be answered.  If so it leads the user which for me is called the student_user to the question/index page.  This page is the main page of the application.  It is where all the questoins are stored.   Each question has a link that leads the sutdent_user to to the question show view.  In this view the student_user is able to view the question that they clicked and all answers that are associated with that  question.  The student user is also able to create their own answer or comment to that question.  

When developing these models I struggled with the concept of params.  I kind of understood it but I had many labeling issues that I had to resolve becuase I may have called my answer a description or a comment.  There which caused my program to break multiple times.  I am getting better but still am not fully comfortable with that concept.  The key I would say is to be consitent with the lableing through out the building process.  So really be concious of what the labels your using when building your database because the project will continually use that labeling. If you dont there will be multiple updates to your database. 

I hope this helped some and It does get better with practice.  :)


