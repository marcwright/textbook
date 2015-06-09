Delivery Tips:

* Think about how long you're talking
* Move quicker sooner, slower later
* Cold Call more often
* Revisit LOs
* Defer questions when appropriate

# Rails Path and Link Helpers

## Learning Objectives

* Utilize path and link helpers in views, controllers of a Rails application

## Named Routes

* Refactor Tunr artists to use helpers
  * named route helpers
    * (editor) artists#create
    * I have a problem.
      * Show `rake routes`
    * The problem
      * duplication of this knowledge
        * **Define** in routes and re-type over and over.
        * We **re-type** the convention, instead of coding the convention.
        * We want to **use** what we defined
      * maintenance
      * human-centric routes aka slugs
        ```
        http://tunr.com/artists/17
        http://tunr.com/artists/17-prince
        ```
    * `rails console`
      * `app.artists_path`
      * `app.artists_url`
      * When?  Why?  Let's read.
        * http://viget.com/extend/rails-named-routes-path-vs-url
  * Search Route
    * route:  `get '/search', on: :collection`
    * search_artists_path

  * slugs
    * human-centric routes aka slugs
      ```
      http://tunr.com/artists/17
      http://tunr.com/artists/17-prince
      ```
    * `rails console`
      * `app.artists_path`
      ```
      class Artist < ActiveRecord::Base
        def to_param
          # url safe moniker
          [id, name.parameterize].join('-')
        end
      end
      ```
      * `reload!` !!!
      * `app.artists_path`


  **We Do**
    * Update
    * Destroy


## link_to

** I do **
  * Refactor Views
    * Index
      * Add thing
      * Link to show page for each thing
** We do ** break the conversion down and build it together.
  * (whiteboard) Write initial, show template, show named_route helper
  * Once again, we are re-typing the convention.  If it's a convention, then we should have code that specifies **and** follows it.
      ```
      <a href="/artists/<%= @artist.id %>">@artist.name</a>
      <%= link_to(@artist.name, "/artists/#{@artist.id}") %>
      # I shouldn't use a string, when I can use an object - clarify intent
      <%= link_to(@artist.name, artist_path(@artist)) %>
      # remove duplication
      <%= link_to(@artist.name, @artist) %>
      ```


    * New
      * Back to list of things
    * Create

** You do **
    * Show
      * Back to list of things
      * Edit thing

** I do **
      * Delete thing
      ```
      # song#show
      <%= button_to 'Delete (button_to)', @song, method: :delete %>
      <%= button_to 'Delete with Confirm', @song,  method: :delete, data: { confirm: 'Are you sure?' } %>
      ```

** You do **
    * Edit
      * Back to list of things
      * Delete thing
    * Update


## content_tag
  * Dash for link_to
  * show source
  * content_tag is in TagHelper
    * show docs

**You do**

* Refactor for songs and playlists

# Lesson Plan - Review Notes

Are learning objectives present and complete?
What is the ratio of talking vs. doing? (60/40, TT/ST-wg vs ST-sg / individual)
What is the level of engagement?
Are exercise plans present?
Any pitfalls with the exercises?
