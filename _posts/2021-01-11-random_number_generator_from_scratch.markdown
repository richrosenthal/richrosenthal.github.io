---
layout: post
title:      "Random Number Generator From Scratch "
date:       2021-01-11 15:35:15 -0500
permalink:  random_number_generator_from_scratch
---


Currently I'm partaking in MLH's Local Hack Day weeklong challenges. One of today's challenges was to create a program that could generate a random number from scratch. You could pick any language but you could not use the built in random generator that most langauges offer. I chose to write my program in C++ as that is what I'm learning on the side while I'm completing my part time program at Flatiron. However, my program I wrote is simple enough that it could easily be translated into any language like Ruby or JS. 

Here is the code I wrote and I'll explain it step by step.
```
int getRandomNumber(){
    
    unsigned long num = time(0) * time(0);
  
    string stringifiedNum = to_string(num);
    
    char charNumber = stringifiedNum.at(9);
    
    int randomNumber = int(charNumber) - 48;
		
    return randomNumber;
}
```

The first line is declaring the function getRandomNumber. The next line is initializing an unsigned long variable called num. (unsigned long could also have been a double or float, I just chose unsigned long). Now I needed to seed my variable with something that could be perceived as random. Computers have a very hard time at creating actual random numbers so this will be a fake random number. However, to the user it will be perceived as a random number. By using time(0) I'm grabbing the computer's time and multiplying it by itself in order to create a massive number that will be perceived as random. I then use stringify the num variable into a string called stringifiedNum. I then grab a random element in the string variable, in this case the 9th element and assigning it to a char variable called charNumber. I then cast the char into an int and that is what the function will return. However, when casting the char to an int, it ends up casting the ascii value of the char. In other words if the char that is printed to the screen is 0 it's ascii value would be 48. To get around this I subtracted 48 from the casted value in order to get any number from 0 to 9. 

Now I do not recommend using my code as a replacement to C++ built in random function or any languages. It is no way an elegant solution but it helps to understand what is going on under the hood and what we sometimes take for granted when using built in functions. 
