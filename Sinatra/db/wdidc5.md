# DATABASES with sinatra

## LO's
### mechanics
- use Active Record on Sinatra app
- execute CRUD functionality with Sinatra
  - executes RESTful routes
  - execute POST, PUT, DELETE request through google postman
- create a Sinatra App with Active Record

## Opening Framing
#### PKI (5m)
- Get in groups of 5 and discuss the following. Write down at least 2 ideas.
- With what you know about active record, sinatra views and routing, how might we integrate them all together(think about your CLI app you made for your first project)
- write on white board student ideas

## We do (Codealong 25m total)
### Lets hop back into our todo application we were working on earlier.

Lets create our database for the todo app(have students walk you through stuff they should know)
- create database
- create/load schema
- create AR class definition in a models foler
- create/load seed file
- create active record connection(include host)

Cool, we're connected. I think it would be really nice if for now, our index page just loaded all of our tasks. (5m)

Awesome! I think it would be even sweeter if i could create a page for a single todo by just putting its id number in the url(5m)

Maybe I could even have the list of todos, link to each individual todo. (5m)
```erb
<p><a href='/todos/<%= todo.id %>'><%= todo.description %> | <%= todo.completed %></a></p>
```

## You do(25m)
update your blog you've been updating to incorporate a database. It should have an index page and a show page.


## We do(codealong 25m)
- notify class that we won't be doing forms until tomorrow, so we will use post man for the CUD in CRUD

Create
```ruby
post '/todos' do
  @todo = Todo.new(description: params[:description], completed: false)
  @todo.save
end
```

Update
```ruby
put '/todos/:id'
  @todo = Todo.find(params[:id])
  @todo.description = params[:description]
  @todo.completed = params[:completed]
  @todo.save
end
```

Delete
```ruby
  delete '/todos/:id' do
  @todo = Todo.find(params[:id])
  @todo.destroy
end
```

## You do (25m)
- update your blog application to have create update and delete functionality through RESTful resources. Test with postman
