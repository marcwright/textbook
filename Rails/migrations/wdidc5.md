## Learning Objectives

- Describe Rails: purpose, major components and their roles
- Generate a new Rails application, including configuration
- Use help for the `rails` command
- Generate a model, with related migration
- Seed database with demo data
- Construct CRUD views for a model

## Overview

- generators
  - `rails new`
  - migrations
- We build tunr
- They build blog

## Why? Connection to Larger Goal

Many of you, most of you, will be working in Rails.  It is the framework of choice for web development (http://www.indeed.com/jobtrends?q=j2ee%2Casp.net%2Cruby+on+rails%2Cphp%2Cdjango&relative=1&relative=1).

## Framing

Board: Rails makes the simple easy, and the tough possible.


Board: What did DHH build into Rails?  What does it do for us?
  "We reviewed the differences between Sinatra & Rails.  Let's talk about similarities.  Let's move a step up, a higher abstraction."

  (we do, 2 min) What do we need to do for our users? the web?
    - present info
    - gather info/data
    - show errors/issues
    - request/response
    - security

  (they do) Focused Listing,  (2 min @)
  What do we need for related Models to function as we have grown to expect?
    - model
    - validations
    - db/table
    - associations

  What do we need to render a helpful, functional html page?
    - template
    - objects/data
    - layout

DHH video [Build a blog engine in 15 minutes](https://www.youtube.com/watch?v=Gzj723LkRJY).  November **2005**.  Warn about "whoops".

-
- (8:30) partials


## Rails Provides (5 min)

- Libraries
- Generators
- Framework: glue, (band) conductor


## Generators: `rails new --help`
 - what is generated
 - configuration

### We Do: `rails new --help`

So, we see that `rails new` is an important tool for the web developer.  You will use it repeatedly while learning.  Rails uses convention over configuration and this is your first opportunity  to configure.  To mold Rails to your liking.  Let's take a look...

`rails new --help`

Lots of stuff here.


### You Do: Documentation Scavenger Hunt (5 min)

1. What command would you use to see what rails new would do, without actually creating the folders and files?
1. What flag(s) will you add to tell Rails to use postgresql?
1. What flag(s) would you add to generate a rails app without Test::Unit/MiniTest?
1. What flag(s) would you use if you wanted to override the default javascript library?


### We Do: Create rails, w/configuration

1. cd class_work.  You should NOT be in a git
1. `mkdir starting_rails && cd $_`  (`$_`: most recent parameter)
1. bundle exec rails new --pretend temp_app
review
1. rails new rails_new temp_app
1. cd, git init, commit
1. bundle exec rails new -d postgresql rails_new
1. compare (gitx)

- Discuss configuration
- Note: **I** don't remember this stuff.  Used infrequently.  That's why we need to know where to find help.

- Speaking of frequently
  - alias be=`bundle exec`

## tunr_rails2

### We Do (generate app)


- `cd class_work`
- prompt for command
  - what do we use for testing? rspec
  - `be rails new -d postgres tunr_rails2 --skip-test-unit`
  - commit my changes
    - git init
    - git add .
    - `git commit "be rails new -d postgres tunr_rails2 --skip-test-unit"`
- rspec-rails
  - Gemfile
  - `rails g rspec:install`
  - review files
- model: Artist
  - Instead of rote memorization of steps - making sure you are **identifying need** & thinking about what tools in your toolbelt answer that need.
  - prompt: what are some responsibilities of the Artist model?
  - dependencies?
    - db
    - table
    - AR model
  **JUST WATCH**
  - 1st dependency: create db
    - `psql -l`
    - `rake db:create`
    - `psql -l`
  - 2nd dependency: table
    - `psql -d tunr_rails_development`
    - `\d`
  - Answer 2 & 3 together.
    - `be rails generate model Artist`
    - What files were created?
- What? no :name?  No problem.
  - `be rails destroy model Artist`
  - What happened?
- re-generate Artist, w/name
  - `be rails generate model Artist name:string`
  - **NOTE**
  - review each file
    - model: what functionality does this give us, AS LONG AS table exists
    - describe & delete fixture
    - test: describe & ignore spec
    - migration
      - timestamp

- 2nd dep: table
  - Is it there? `psql -d tunr_rails_development`, `\d`
  - run migrations
    - `rake db:migrate`
  ** WATCH **
  - review migration
  - review psql
  - review db/schema

### Add photo_url

- `rails g migration add_photo_to_artist photo_url:string`
- clarify naming convention, indicate more in docs

### Migration
  - just one step of many
  - The database is setup by running all these migrations, in order.

  - supports the team



### rails console

- Remember how it was kinda painful to verify/play with our models in Sinatra.  We had binding.pry in app.rb, sandbox.rb, seeds.rb.  It's possible, that it's still not clear.
- Rails provides `rails console`
- `Artist.create!(name: "Sweepstakes")`


### rake db:seeds
- Do we want to create all these Artists manually?  
- What was the name of the process that we use to populate the db?
- Where would expect Rails to put the file for this step?
- `db\seeds`
- `rake db:seeds`

### You Do: Add Songs



## Closing:

Have student show working web app.  Have that student review the first learning objective.  Work through other objectives, asking other students to indicate which part of that app demonstrates the objective.
