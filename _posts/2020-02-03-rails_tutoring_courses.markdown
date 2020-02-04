---
layout: post
title:      "Rails Tutoring Courses"
date:       2020-02-04 00:34:30 +0000
permalink:  rails_tutoring_courses
---


The Rails project was a challenge it required for me to use various relationships, user authentication, various validations, and DRY. These requirements led me to question my abilities.  But now that I’m up to my third project I think that is commonplace for me.  It’s going to be a little scary, intimidating, and difficult but just plow forward because the knowledge that you gain when being pushed to your limits is what’s going to develop your skills.   

I started my project by whiteboarding my relationships, classes and tables that I would need in order to complete this assignment.  I thought about what I would need if I was building a place where students and teachers interact in order to administer and submit assignments and courses.  When thinking there will be a user, that will have two status's a teacher and a student. There will also be enrollments, assignments, courses, and submissions.  These were the tables that were created, and they became tied together through various relationships.  Visualizing through whiteboarding helped me be able to see how each of these tables will relate to the other.  Another skill that I was able to work in with white boarding was creating the flow for the application.  It helped me make a plan with how the routing will work for the application. 

The user login and authentication was done through the gem of Devise.  I found that this was extremely helpful because it was able to build out the user.  It created the password security and was able to have the user model get started.  The other gem that I used to help with login and authentication was OmniAuth.  This gem allowed the user to be able to login from another source.  This was also a way to verify the user as well as gain further information about that user from the information that was inputted into the other site.  When researching the OmniAuth I did find that it would also be extremely useful if the site that you would use would be something that would give you dual purpose for your application.  

One of the challenges that I encountered when completing this project was when I had a link_to that was not executing.  The problem was the lack of explanation in the errors in the Puma gem.  For some reason the same link_to route that worked on other views was not working on my assignments index view.  

<li>  <%= link_to  "Add Assignment", new_course_assignment_path(@course)%></li>

This was frustrating.  But sometimes frustrations leads you to research.  The lack of information with the puma gem led me to install the better_errors gem that at least gave me errors.  Unfortunately with that one link_to the syntax refused to work and I had to use a different routing syntax to be able to complete the tasks.  


Being DRY is something that I definitely struggle with.  I think that getting the application completed is imortannt and I will have to make sure that  i dont repeat myself in the code to keep it DRY.  



   

