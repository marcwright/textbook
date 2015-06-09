![](http://www.kylembrown.com/wp-content/uploads/2013/11/logo.png)
# Sinatra Views

## Learning Objectives
### Concepts
- Explain what ERB is and why we use it.
- Explain the convention over configuration in relation to Sinatra.

### Mechanics
- Use ERB to execute Ruby code in the view templates.
  - <% %>
- Pass a variable from the main Sinatra file and use it in a view.
- Use a layout view file to set a common theme for all your views.
- Explain what yield does in regards to a layout views.
- Override a default layout with a specific layout.


#### Opening Framing
Let's check out a popular website.
- talk about how their are a lot of similarities from page to page
- it would be really nice if we could consolidate our html into groups that will be consistent throughout the page. Enter sinatra views..
- today will be lots of coding, we'll be moving quickly so we can have alot of application time

### Sinatra Templates/Views
- What is a template?
  - A template in Sinatra is simply a file which contains the HTML we want to display.
  - This file is kept separately from the main program file in order to achieve a level of separation of concerns.
  - Templates can also accept a variety of data from the main program file and display different information based on what they receive. But it doesn't have too.

### We do(codealong 30m)  
Let's hop into some code to see some Sinatra Views in action. Let's first make a working directory `$ mkdir todo`

Go into that directory and lets do a `bundle init`

Modify Gemfile to include our dependencies.
```
source 'https://rubygems.org'

gem 'sinatra'
gem 'sinatra-contrib', github: 'sinatra/sinatra-contrib'
```

Let's make sure our dependencies are working by creating our main `app.rb` file and doing a quick hello world.

```ruby
require 'sinatra'
require 'sinatra/reloader'

get '/' do
  "hello world"
end
```

`$ bundle exec ruby app.rb`
Great everything's working, lets create our first views. In order to do that let's consolidate our views into a `views` folder. Make sure it's named correctly. Sinatra knows to look for views only inside the `views` folder.

#### Convention over configuration
- follow conventions and things will be configured correctly
- don't follow conventions, you're going to have a bad time
- talk about how they've already been dealing with some convention over configuration in active record, and how it'll be super important going forward into rails

lets go ahead and make a view file
```bash
$ touch views/index.erb
$ touch views/show.erb
```

now lets change the get request to:
```ruby
get '/' do
  erb :index
end
```

- fill some dummy content into index files
- add some more routes using the 2 different erb's

### Class Exercise(30m)


### We do(codealong 20m)
- so you might be thinking, this is nice, but i still have to code all of the html, what if there are parts that i want to keep consistent throughout views

#### The Layout View
- Many, if not most, websites tend to have a common visual theme.
  - In order to accomplish this on our Sinatra applications we will use a Sinatra convention called the layout view.
  - By creating a `layout.erb` file in our views directory we tell Sinatra we want this structure used across all of our views.
    - This is useful for having a common header/footer/navigation on every view in our app without having to add that code into each of our view folders.
- The problem is in figuring out how our layout knows which different view to render.
  - Without the proper structure and keyword, all our routes will render the layout.
- sinatra will actually look automatically for `layout.erb` in your views file. If it doesn't exist it just loads the view inside the request without a layout.
- Let's make that file now `$ touch views/layout.erb` and edit it:
```erb
<!DOCTYPE html>
<html>
  <head>
    <title>Personal Blog</title>
  </head>
  <body>
    <%= yield %>
  </body>
</html>
```
- The important part is this chunk:
```erb
<%= yield %>
```

### Yield
- the `yield` keyword tells Sinatra, that at this point in the document we should render the view that was specified in the main application file. The symbol following erb in the routes.
- show this in code by manipulating the layout and checking two different routes

### Refactor your existing code to incorporate a layout(20m)

### We do(codealong 20m)
### <%%> What are these things?
- these tags will allow you to embed ruby into your html, crazy.
- lets change the content of one of our routes and use embedded ruby in one of the views


```ruby
get '/' do
  @todos = ["todo1", "todo2", "todo3"]
  erb :index
end
```

```erb
<h1> todos </h1>
<% @todos.each do |todo| %>
  <p><%= todo %></p>
<% end %>
```
### refactor to incorporate erb(20m)






#### multiple layout, if there's time
```ruby
get '/some_route' do
  erb :some_view, :layout => :different_layout
end
```
### Resources
- [Sinatra Docs](http://www.sinatrarb.com/)
- [Rails Girls Guide - Sinatra](http://guides.railsgirls.com/sinatra-app/)
- [Sinatra on GITTR Blog by Chris Schneider](http://gittr.com/?cat=8)
