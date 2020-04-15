---
layout: post
title:      "The Joy of Hackathons!"
date:       2020-04-15 16:52:33 +0000
permalink:  the_joy_of_hackathons
---


One of the things I have felt far more confident in attending since I started my journey at Flatiron is attending Hackathons. Actually it was at my second hackathon after talking to a Google student ambassader that I made the decision to attend Flatiron in order to prepare myself for SWE internships. Since joining Flatiron, I feel like I'm actually able to be more competent in writing code and not a drain to my hackathon teammates.

One of the my favorite things about hackathons, besides all of the SWAG, is the ability to attend workshops and try out new technologies. At my most recent attended hackathon I attended a workshop by Google which introduced me to the many services that are offered on GCP. After attending the workshop I had an idea of using their maps API to create a program that would allow end users to check Covid-19 symptoms and based on their answers show them a map of local hospitals. 

Because I had just finished my Sinatra project for Flatiron the day prior to joining this hackathon, I decided to use the Corneal Gem in order to create a skeleton MVC project to get started. Everything was working flawlessly until I realized that due to the code in the generated layout file, the my map was not displaying markers for local hospitals. After working with the guy who presented the Google workshop and looking through documentation we realized that the cause was due to a confliction with the layout file. I was attempting to fix this but I was getting close to the deadline to submit my hackathon project. 

As in all hackthons, changing the direction for your project happens all the time. So I ended up pivoting to using the Twilio API. So using everything I had created already, sans the MAP, I changed the forms so the end-user could input their symptoms and based on that the app would send an SMS to their doctor (or to whomever's number they had inputted). 
And it turns out the Twilio app is extremely easy to use in Sinatra. 
```
@map_key = ENV['Maps_Key']
account_sid = ENV['TWILIO_ACCOUNT_SID']

auth_token = ENV['Twilio_API_KEY']
client = Twilio::REST::Client.new(account_sid, auth_token)

from = 'Add issued number here' # Your Twilio number
to = "+1#{params["phone"]}" # Your mobile phone number

client.messages.create(
from: from,
to: to,
body: "Patient (#{@name}), living in #{@city},#{@state} is at risk and has the following symptoms: #{symptoms}.
      and is age: #{@age}. #{preexistingcond}
      "
)
```

With just this code, and of course adding it to your gem list, I was able to send SMS. It was really cool using this and I'm looking forward to implementing this in future projects. Now while I didn't win any of the tracks, I felt like I accomplished something with everything I have learned so far in bootcamp and that in itself was the real prize!

Also, I cannot stress enough to never ever ever upload code to github that has your API key and Twilio number.....It was a $50+ lesson I will not soon forget. 
