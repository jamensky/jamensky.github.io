---
layout: post
title:      "CLI Project - Actorinfo"
date:       2020-03-16 23:53:20 +0000
permalink:  cli_project_-_actorinfo
---



                                                            
For my CLI project I have created a program that will allow the user to retrieve specific information relating male actors of age 40 years old or below. The entire application is designed in Ruby. The following is a general break-down of the process and the tools I have used in order to design and build this project. 


**1 - Set up the Git repository & basic files and folders**

The first thing I needed in order to begin my project, was a Git-Hub repository. Essentially what a Git-Hub repository does is to record and store different stages of the project, each stage being the last time I saved or "committed" the project. This helps with tracking the development progress as well as being a form of storage for all the files and folders that make up the application. 
Once the repository was all set and ready to go, I needed to set up the basic file structure of the application. There are various ways to go about doing this, the one I used was through the "bundle gem" command via the terminal. This command will automatically set up the basic files and directory structure needed to describe, test, and also publish a gem (a gem is a Ruby application). Files such as the README, Rakefile, a Licence, etc, will all be automatically provided and adequately structured through this command. 


**2 - Find a Scrapable Website** 

At this stage I begun looking for a website that would allow for scraping to be perfomed. This was probably the most time taking task as most websites do not allow for scraping, unless permission is granted by the website owner. Although this was the second step, In retrospective, I would now advise anyone to put this at first priority, since you may not find a scrapable website for your project and you may end up having to make major changes to the objective of your project. Which is what happened to me. Initially I was planning to scrape data about movies, and only after I created the Github-repo and gave it all related titles and names, I figured that every website that had what I was looking for did not allow for scraping. And so, I had to scrap the entire project and begin a new one. 
The method I used for finding out if a website allows for scraping or not, is by entering "/robots.txt" right at the end of the http link. For instance, "https://www.listal.com/robots.txt". This will direct you to a separate page outlining what is and was is not scrapable on the site. 


**3 - Code Structure** 

I broke down the entire code structure of the app into 4 interconnected classes;

1) CLI Class: This is the command line interface controller which will host all the code I will be using for the purpose of managing all interactions between the user and the application. This will be done by printing out welcome messages and instructions on the terminal, to guide the user through the services offered by the application. The primary method used in this class is the "gets" method, which allows for the user to give input to the application and ultimately navigate through and use all its functionalities. Through this method the app will also acquire basic personal information about the user which will then be used to create a User class instance. This user instance will essentially be the equivalent of a personal user account. 

The CLI class will be able to access the other three classes, in order to call on their functionalities. This will be done via the "require_relative" method, not to be confused with the "require" method which is a method for requiring external gems/files/applications, whilst "require_relative" is for requiring relative files, as the name rightfully suggests. Relative files are files that are located within the same project directory.  


2) User Class: Here we will be storing and saving two pieces of data about the user in the form of a class object with the user info assigned as attributes; their name and the actor they have entered as their choice. These details will be saved and will be accessible by the user.


3) Scraper Class: This class will be responsible for scraping the website. To scrape a website is to simply access it and extract from it any type of information that is available in it. Scraping in Ruby requires two applications to be installed. 
The first one is Open-Uri, which allows for our program to access and interact with the targeted website, and Nokogiri, which is a program that is able to extract and parse HTML and XML data from the targeted website, and organize this data into elements within an array, making  it easy to access and manipulate. The information the user can request from our application is limited to 3 pieces of data; the actor's age, date of birth and place of birth. Upon the user entering the name of the actor, our Scraper class will first check if the actor is available by running a quick scan and match, if the name is found on the website it will automatically create an instance of the Actor class assigning it the three pieces of data as instance attributes, and via the CLI file return a message asking the user for the type of information they would like to receive. 


4) Actors Class: This will be our class for generating and storing instances of actors as they are being requested by the user. Here we will also host all the functions that will evaluate and return the type of information about the actor the user wants to learn more about. 


**4 - One File to Run Them All - actorinfo.rb**

This will be the single file we will need to run in order to access and run all the other files, and therefore the entire application. Here we will require_relative the CLI, the Scraper and the User files. With this all a user would need to do in order to use this application is to clone its Git-hub repository through the terminal and simply enter "actorinfo.rb", also via the terminal. 







