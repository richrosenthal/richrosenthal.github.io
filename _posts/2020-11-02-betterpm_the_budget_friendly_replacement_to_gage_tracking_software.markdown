---
layout: post
title:      "BetterPM: The budget friendly replacement to gage tracking software"
date:       2020-11-03 00:36:08 +0000
permalink:  betterpm_the_budget_friendly_replacement_to_gage_tracking_software
---


So this was definitely the hardest project I have put together to date. JS was quite a bear to learn. I constantly felt stuck and had to go back to fully understand even simple topics (I'm looking at your fetch requests). However, I feel that I now have a much better understanding of JS and feel much more comfortable working with it.That being said, I realize I'm only scratching the surface. 

For this project I borrowed heavily from my sinatra project when designing a BetterPM, like that project I wanted to base it off of a problem I am facing at work. As a document controller one of my many jobs is to track all the paperwork and maintenance done on every single piece of equipent owned by the company and then create reports for upper mangagement for when we go through our yearly audits. The software we currently use is extremely clunky and not user friendly at all. I'm constantly on the phone with IT who then are constantly on the phone with the company that created the software. Needless to say, we end up wasting valuable time. 

My project aims to fix this by recreating it as a web application without all of the bloat. This project is still in its infancy. Right now my main focus has been on getting several CRUD functions working between the backend and the JS frontend. 

The fetch requests were originally giving me much trouble. But once I took the time to understand them it was quite easy. While working on this I spent two days trying to figure out why my tasks were not persisting to the database. I had originally thought I had messed something up with the serializer but it turns out that I had never actually whitelisted the params for the "equipment_id" portion of the task model back in the backend. After spending what felt like forever I finally finished the final piece of the puzzle needed to finish this project. I learn so much with vanilla JS but I can't wait for React!
