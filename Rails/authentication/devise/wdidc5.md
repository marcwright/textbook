# Devise! and sessions

## Learning Objectives
- explain how sessions give state to a web application
- explain how user authentication utilizes sessions
- set session hash key value pairs inside of a rails application
- implement user authentication into a web application utilizing the devise gem
- implement useful helper methods devise provides

### Opening Framing (10m)
- So we've figured out how to execute CRUD functionality into our apps. This is great, but should whoever stumbles upon our application be able to do whatever they want? It would really suck if your buddies could post for you on facebook or if someone withdrew money from your banking site.
T & T
- Well, that shouldn't be the case. For the next 5 minutes turn to your partner in class and discuss how we might be able to prevent people from doing whatever they want on your website.

- Write student responses, extrapolate and get students to think about sessions or at the very least a User model or signing in


## Enter Sessions(i do, talk + setup)15m
- HTTP is stateless, so it's up to either the browser or application that needs to "remember" what's happening
- A session is just a place to store data during one request that you can read during later requests.
- A session is a hash containing key value pairs that provide state in your application

Let's hop into some code so we can see sessions in action.

We have a simple CRUD app for a "blog". I've only defined the index, show and create routes for this app and only have two views thus far.

Have everyone pull the rails app, and run the setup commands.
## We do code along(25 m) understanding how to set and use session key-value pairs
Encourage students that just watching is fine, but if they want to code along that's fine as well.

```ruby
# add code to posts controller
def testing_session
  session[:test] = "this is a string stored in a session"
end

# also add @test = session[:test] to index action
# create testing_session.html.erb and add content that we are saving a session variable
# add content to display session[:test] in index view
# add (get '/posts/testing_session', to: 'posts#testing_session') to routes.rb
```
- start at index route
- point out there is no session[:test] yet being displayed
- go to testing_session route
- go back to the index route. See that the session[:test] now exists
- open incognito window(show that no session[:test] exists)
- repeat steps, clear cookies, repeat steps
- hammer in this idea of state through sessions
- add `session[:recently_viewed_post] = @post.body` to the show action
- create `@recently_viewed_post = session[:recently_viewed_post]`
- show it changes after we click a post's link
- show that we can infact store attributes of our models within these session key value pairs
  - to include id's of a user model, which is basically what devise is going to do for us when a user "signs in"
- add `session.delete(:test)` to index route, to show that we can also delete a key value pair from the sessions hash
  - this is whats happening when a user "logs out"

### You do
Take the next 5 minutes to:
- create a new action in the posts controller that instantiates a session key-value pair
- save it to an instance variable in the index, and have it display in the index view

### Break 10m
## Reframing
Devise is a gem in rails that we use in order to streamline user authentication. We're going to talk about how to get devise up and running and a couple of helper methods.

## Devise We do codealong (50m)
- the first thing we should do is add the devise to the Gemfile and run a bundle install
- next install devise then generate the devise User

```bash
bundle install
rails generate devise:install
rails generate devise User
```
You may have to restart your server at this point.
Run rake routes, and show and explain some of the routes.

* add this if its erroring to config/environments/development.rb
`config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }`

Go to log in/ signup pages. Sign up and log in.
Add `<h3><%= link_to 'Signout', destroy_user_session_path, :method => :delete %></h3>` to layout file
Well, cool. We're signed in, but what does that really do for us?

To find out, I want to add a couple of things to our code.
- i think it'd be nice if users could have their own blogs. So let's update that.
- add `has_many` to user and `belongs_to` to post
- add column `rails g migration add_foreign_key_to_posts user_id:integer` and then run migrations
- when you get to the User model, there's a bunch of methods, if you look at devise documentation they'll explain what each do, they are towards the top.

### Devise implementation
- Cool, now that we got everything setup, lets go into our posts controller and change some things up.
  - change index action to have just current users posts
  - change create action to create a current users posts
- go back to index page, and note that all the posts went away, because they didn't belong to the user thats signed in.
- create some posts as a user
- log out, and log in as a different user show that there are no posts associated with this user
- log back into the original user, and show the posts that you created before
---

- open new incog window, try to access posts index directly and get an error message
- current_user is nil, why?
- do if current_user `@posts = current_user.posts`
- else `@posts = Post.all`
- add `before_action :authenticate_user!` and then try to access posts index directly again.

### Break 10m

## Class Ex
- Take an existing application you've created in rails, and add user authentication with the devise gem.





https://github.com/plataformatec/devise
http://www.theodinproject.com/ruby-on-rails/sessions-cookies-and-authentication
