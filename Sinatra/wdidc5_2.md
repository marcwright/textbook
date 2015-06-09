Delivery Tips:

* Think about how long you're talking
* Move quicker sooner, slower later
* Cold Call more often
* Revisit LOs
* Defer questions when appropriate

# Intro to Sinatra

## Learning Objectives

* Distinguish between a route and a path
* Describe what a web application is and what it is used for

#### Mechanics

* Build a Sinatra app that responds to HTTP requests
* Define routes using Sinatra to respond to GET requests
	* Static
	* URL parameters

## Outline

### Intro

**The Talk**

* Route vs Path
* File model vs resource model
* A program to take incoming requests to different routes to perform different
actions

**Check for understanding - open questions**

### Our First Sinatra

**I do**

* Frame the Sinatra documentation dive

**You do**

* [Sinatra Documentation](http://www.sinatrarb.com/intro.html) dive
	* Readme - Getting Started
	* DSL link
	* Example

**Check for understanding - trench walk**

**We do**

* Build "Hello World Sinatra app"
	* Set up new folder
	* Create app.rb
	* We need sinatra! gem install sinatra
	* Set up get '/' and just "Hello, World"
* Curl your hello world sinatra app!
* Now look at the browser!
* WHOA! **Trace the request from client to server and back**
* Additional paths
	* Add a constant path
	* Add a path with a URL parameter

**You do**

* Set up a Sinatra application called `jokes_app`
* Set up a route `GET '/'` that returns a hello message
* Create a custom route `GET '/jokes'` that returns a joke
* Create a custom route `GET '/:name'` that returns a personalized hello message
* Create a custom route `GET '/jokes/:name'` that returns a personalized joke

**Order of routes!**

# Lesson Plan - Review Notes

Are learning objectives present and complete?
What is the ratio of talking vs. doing? (60/40, TT/ST-wg vs ST-sg / individual)
What is the level of engagement?
Are exercise plans present?
Any pitfalls with the exercises?
