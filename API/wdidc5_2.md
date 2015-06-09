# APIs and Sessions (Recap)

## Learning Objectives

Sessions:
* Explain what `sessions` are and how they work in rails.

APIs:
* Describe what an API is, and why we might use one.
* Explain how a rails app can communicate with an API.
* Explain the common role of JSON on the web.
* Use an API (via HTTParty) to gather external data and present it in a
  rails application

## Overall Outline

Today we're going to focus on APIs, but since classes didn't both see sessions,
I want to recap that. They are a useful part of Rails and web development in
general.


## Sessions Outline

Demo sessions app.

## APIs Outline

Question: So far, what has been our 'job' as web developers with regards to HTTP?
Answer: To write code that responds with HTML.

### What are APIs

Sometimes, we may want to build a web service (app), that depends on other services
(apps). The way our app can communicate with another app is via an Application
Programming Interface.

Break down the name: API.

There are lots of different APIs (in different languages / protocols). When we
use rails, in a sense, we use the Rails API (the set of public methods we can
call from our program into Rails.)

Most APIs on the web are over HTTP. Our app will make GET, POST, etc requests
to get or modify information.

Demonstrate making a request in Chrome for:
`http://api.giphy.com/v1/gifs/search?q=funny+cat&api_key=dc6zaTOxFJmzC`

What does this look like? (A Hash)

Show them the JSON Formatter Plugin. A big part of dealing with an API is
navigating the data returned.

#### A Note on Authentication

Some APIs are partly or wholly protected by login, usually as both the developer
and the person you're acting on behalf of. This is called OAuth, and is outside
of the scope of today's lesson.

### Using APIs

So we need a way to **make** HTTP requests in our app. Thankfully we have tools
to help us with that. Ruby has a built-in HTTP library, but HTTParty is way
much better.

Show the HTTParty docs, then demo making a GET request in the terminal to the
giphy API. Show how the response has been parsed from JSON to what acts like a
normal hash.

Write Pair Share:
Let's say we wanted to show users the search results from the giphy API.
Describe how you might implement that. What views, controllers/actions? Do we
need any models?

Recap:
Probably want a search form (and controller action to display it)
Probably want an action to handle submission of the form.
  It should search the API and render the results.

What if we wanted to let users 'favorite' gifs? Assume it's temporary, no models.
Sessions! Session can hold an array and we can append something to the array.
Would we append the gif itself? NO! We almost never do something like that on the
web, instead we store IDs (or the like.)


## Exercise

See ex_giphy_favs.md
