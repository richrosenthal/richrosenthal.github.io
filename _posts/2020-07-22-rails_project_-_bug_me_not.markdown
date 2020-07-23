---
layout: post
title:      "Rails Project - Bug Me Not"
date:       2020-07-23 02:54:10 +0000
permalink:  rails_project_-_bug_me_not
---


> So my idea was to create a project management and bug tracking application for my Rails project. It is something I plan on using to log bugs I encounter in future projects so I can easily look back at different bugs I have encountered. 
> This has been quite a learning experience. 
> 
> 
> One of the longest roadblocks I had faced was my Tickets not saving to the database. I would fill out the form for creating a ticket, try to pick a project and submit it. And while it was not throwing up any errors when I would check what SQL commands were being fired in my terminal I saw that it was not saving to the database. I spent two hours searching the internet, picking through my code, until I realized what my mistake was. In my tickets controller, I had written this `@ticket.user_id = session[:id]` when I should have written `@ticket.user_id = session[:user_id]` This was such a tricky error because it initially did not cause any issues on the surface. 
>

Another roadblock I had ran into was trying to create a link on the Tickets index page to the nested route. After an hour of google searches I realized that my link_to path had required an id param to be passed to it. I had initially been sending it zero arguments. 

I'm looking forward to learning frontend development because while the app is functional, it's not the most user friendly. 


