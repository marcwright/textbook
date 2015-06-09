Delivery Tips:

* Think about how long you're talking
* Move quicker sooner, slower later
* Cold Call more often
* Revisit LOs
* Defer questions when appropriate

# Frame Week

Monday:    Rails MVC, Migrations
Tuesday:   Link & Form Helpers
Wednesday: Validations / Agile Workflow
Thursday:  Review Session / Lab (Practice Rails)
Friday:    NO CLASS!

Monday:   User Auth
Tuesday:  Project 1

Homework: More code to review now, so if you rate your comfortability and
completeness as high, we may not give it as much scrutiny. However, if you put
questions in your PR description, we'll use those to focus our feedback.

# Intro to MVC

## Learning Objectives

* Explain what Ruby on Rails is and it's architectural components (rMVC)
* Explain the lifecycle of an HTTP request in Ruby on Rails
* Explain how Convention over Configuration relates to Ruby on Rails
* Explain the structure of a rails application (folders & files)
* Create a new Ruby on Rails application
* Create a Rails App with a RESTful interface
* Follow Rails naming conventions when creating models, views and controllers

## Outline

### Why Rails?

* frameworks: common solutions for common problems
* designed to enforce best practices (MVC, REST, TDD)
* teams! very efficient to get up to speed

#### Convention over Configuration

* Reduce code we have to write, as long as it follows the conventions of the
  framework.

#### Compared to Sinatra

* Enforced directory structure
* Asset pipeline
* Testing built in
* ORM built in
* Migrations
* LOTS of other features

(Gemfile, DB config, config.ru, testing, environments, rake tasks)

What are we focusing on today?

* rMVC Architecture
* File Structure
* Migrations

### MVC Architecture

Draw a diagram of the clients and servers, and review the idea of request /
response.

The server can handle the request in any way it wants. Let's look at how
MVC would handle it.

Draw a diagram of the rMVC process. Use the analogy of a corporate building:
* Router:     Receptionist
* Controller: Department
* Model:      Looking in the file cabinets, searching their records to find the
  info you need.
* Views:      They write up a standard report, filling in the blanks based on
  the info that they found.

[Diagram](http://darynholmes.files.wordpress.com/2008/03/routinginrails.png)

#### File Structure

Init tunr app:
    rails new tunr --database postgresql

Explain how our diagram maps to the files in a rails app.

Explain:

* app folder
  * controllers
  * models
  * views
    * layouts
* config/routes.rb
* config/database.yml
* db
* log

### Getting Started with Rails

Port Tunr from Sinatra to Rails (just artists), and then students port songs
and playlists.

# Lesson Plan - Review Notes

Are learning objectives present and complete?
What is the ratio of talking vs. doing? (60/40, TT/ST-wg vs ST-sg / individual)
What is the level of engagement?
Are exercise plans present?
Any pitfalls with the exercises?
