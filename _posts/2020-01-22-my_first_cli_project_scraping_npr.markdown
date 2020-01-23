---
layout: post
title:      "My first CLI project (Scraping NPR)"
date:       2020-01-23 04:15:35 +0000
permalink:  my_first_cli_project_scraping_npr
---


This was the first web scraper I have ever created. It was quite the grind; however, I have learned so much after building this application. I will admit that I am quite the public radio nerd. For my project I chose to scrape the NPR website. One of the challenges that I had faced was implementing the Nokigiri gem into my project. While it was initially difficult to wrap my head around the usage of Nokigiri, thankfully the gem is well documented. I spent a good portion of my time reading through the documentation on https://nokogiri.org/ in order to correctly implement it. 

One of my character flaws is my hatred for debugging. I'm an instant gratification type of person, so the thought of slowly combing over my code is not at all appealing. However, debugging is extremely 

One of my biggest hurdles was creating a scraping method. 
```
def self.make_stories
   doc = Nokogiri::HTML(open("https://www.npr.org/sections/news/"))
   stories = doc.css("div.item-info")
    stories.each do |item|
      story = self.new
      story.headline = item.search("h2.title").text.strip
      story.summary = item.search("p.teaser").text.strip
      @@all << story 
    end
   end 
```

I spent well over an hour trying to get my stories variable to store the contents of doc.css("div.item-info"). I had completely forgotten to include "div" in the parameters. I had originally written it as doc.css("item-info") and kept returning nothing. That is where I fully benefitted from using "pry" as well as IRB on my mac. Through careful debugging I was finally able to get my program to properly scrape NPR's website. Completing this project has been extremely fulfilling and I can't wait for the next one.
