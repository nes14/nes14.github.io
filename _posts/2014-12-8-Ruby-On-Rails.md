---
layout: post
title: Intro to Ruby on Rails
---

#Ruby on Rails
- What is Ruby on Rails?
- How Do I get started?

##What is Ruby on Rails?
Ruby on Rails is a framework used to build web applications. It is a front end & back end building tool. Github, Hulu, and Twitter run on Rails. Ruby is the programming language used to make web applications on Rails. Ruby on Rails was created in 2003 by [David Heinemeier Hansson](http://david.heinemeierhansson.com/). Rails was designed to make building web apps easier. Rails helps you by providing you with the framework you might need and thus you write less code.

>Ruby on Rails® is an open-source web framework that’s optimized
for programmer happiness and sustainable productivity. It lets you
write beautiful code by favoring convention over configuration.
-http://rubyonrails.org/

#Getting Started
I am running everything on a Mac so everything might be a little different if you're working on a Windows computer. 

1. We need to check if everything is up to date. 
- Ruby
- Rails
- Gems
- Misc.

Open up your terminal and check the current version of ruby.

```Ruby
$ ruby -v
```

It is very important where you put the minus sign in the correct spot. Trust me. You should be running Ruby 2.0.0p481 or anything that is 2.0.

###Databases

```Ruby
$ sqlite3 --version
```

Qlite3 is the default database platform that will work with ROR right out of the box. So it is important that we check which version we have installed. I am currently running 3.8.5. 

###Next we must install rails on our system.

```Ruby
$ sudo gem install rails
```

I have tried installing rails without including 'sudo' but that just doesn't work for me. I am running rails 4.1.8 on my system. Anything above 4.1.1 will work just fine. 

```Ruby
$ rails -v
```

###Where we are so far
At this point we have rails, ruby and the database installed and up to date.
We are going to create a simple web app on our system and run it locally by creating a local server. (I know that sounds like some hacker stuff) 

###Help 
By running the following code you will be met with some very helpful information on what the keyboard shortcuts are for rails.
```Ruby
$ rails -version
```
###Ruby Make New Please
When we want to create something totally new, we just tell our terminal to create something new using rails. We don't even have to say please!
```
$ rails new blog
```
But it we want to put it in a specific place we can do this
```
$ rails new ~/Desktop/FolderNameHere
```
You'll notice that rails is doing all of the work for you. It is making all of the folders it thinks you might need. This next line will switch to that folder.

```
$ cd Desktop/FolderNameHere
```

***
Now that you are in the folder, running this next line will turn on your server.

```
$ rails s
```

How do you know your server is up and running? Open up a browser window and enter `localhost:3000` You should be met with a lovely welcome.  `Ctrl-C` will turn off your server. 
***

##Hello World!
I have found that is runs best after shutting down the server. From your main folder, running the next code snippet will make rails create a few folders that will help you say 'hello, world!'

```
$ rails generate controller welcome index
```

What we have just done is tell rails to create a controller called 'welcome' with an action called 'index'. In your favorite text editor, navigate to your folder that we have created and open up `app/views/welcome/index.html.erb`. Delete any/all of the text and you can have it say whatever you want. This will be our home page. We know that but Rails doesn't know that. So we have to let them know whats up. 

So lets open up `config/routes.rb` and do some light typing. Uncommenting line 8 `#root 'welcome#index'` will tell rails that any inquiries to `localhost:3000` will be directed to your `welcome/index.html`. 

So lets start up the server again and go to the local host page. 
