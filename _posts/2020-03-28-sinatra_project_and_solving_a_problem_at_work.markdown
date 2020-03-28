---
layout: post
title:      "Sinatra Project and solving a problem at work"
date:       2020-03-28 12:02:29 -0400
permalink:  sinatra_project_and_solving_a_problem_at_work
---


So after nearly using up all of my grace period for the time allotted for my Sinatra project, I have finally finished. I may sound like a broken record but this has been quite a learning experience. I learned so much with MVC design and shoutout to my cohort lead for helping me when I got stuck. 

I had so many different obstacles that were thrown at me during this project from getting called to serve jury duty right when I had started to Covid-19 being just a thought in the back of my head to something that had fully consumed my attention every waking second. But alas, I was able to complete my project just in time. 


My idea for my project was to solve a problem I had been facing at work. At my current job we keep a list of every piece of equipment in the plant logged in a database. The purpose is so we can track when calibrations or maintence is due on each piece of equipment. However, the software we are currently using to access our database is extremely limited and clunky. Several weeks ago my boss had asked me to print out a list of all calibrations that were due the previous year so we could analyze the timeliness of servicing each piece of equipment. The problem with our current software is that it overwrites the previous due date with when it was calibrated, so we lose sight of our timeliness. We are able to pull up manual paper records but it is tedious and time consuming. 

This seemed like a perfect problem to model my Sinatra project on. Using Model-View-Controller design, I built a web application that allows users to sign up and/or log into a website and create gages (pieces of calibrated equipment in manufacturing) and add several key dates for metrics. The user can create, edit, and delete a gage. The gage has several attributes that would help with metrics like when it was created, when its calibration is due, and when was the previous calibration due for it. (Something so simple, yet a much needed feature for my metrics at work). 

One of the biggest problems I had faced when developing this application was remembering all the steps involved in building a database and migrations. 

```
class CreateUsers < ActiveRecord::Migration
  def change
    create_table :users do |t|
      t.string :name
      t.string :password_digest
      t.string :email
    end
  end
end
```

When building my user migration I realized I needed to use "password_digest" with the bcrypt gem and not simply "password." This bug ended up causing me more grief than I would like to admit. Once I realized that I tried manually changing it in my schema and couldn't understand why it was not working. It turns out I needed to roll back my migration and remigrate in rack in order for my application to be happy. 

The amount of errors and searching I did to fix this bug has made me far more comfortable using a database. 
My hope in the future is to add an automation due date and previous due date calculation for my application to make my app even more robust and time saving. 


