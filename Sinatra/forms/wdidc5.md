Delivery Tips:

* Think about how long you're talking
* Move quicker sooner, slower later
* Cold Call more often
* Revisit LOs
* Defer questions when appropriate

# Sinatra Forms

## Learning Objectives

* Explain the general structure of a form
* Define the purpose of the 'action' and 'method' attributes of a form
* Explain how inputs and their names map to params in sinatra
* List common HTML inputs and their purposes
* Differentiate how data is sent in a 'post' form vs a 'get' form
* Write forms that submit data to a sinatra app
* Write forms that use nested parameters

## Outline

We clearly see the need for forms in our apps, right? Right.

### Forms Structure

**I do**

Discuss the role of forms:

* Forms submit structured data
	* action: path
	* method: verb
* Inputs are the fields to enter data
	* name: key in params hash
	* the submit button to perform POST request
* Data gets put into `params` hash
* Post some data with a POST request and view it

Explain the of a form
```html
<form action="/todos" method="post">
  <label>Description:</label>
  <input name="description">

  <input type="submit" value="Create">
</form>
```

**We Do**

Add a 'new' form to the TODO app.

**You Do**

Add a 'new' form to your blog app.

### Think Pair Share - What's different about an edit form and the update action?

Ans: prepopulated, includes an ID, PUT method.

**I do**

Demonstrate a bare-bones form that has a put method

```html
<form method="post" action="?????">
	<input type="hidden" name="_method" value="put"/>
	...
</form>
```

**You Do**

* Add an 'edit' form to the Todo app.
* Reconvene
* Add an 'edit form to the blog app.

## GET forms

*I do*
Create a `get` form that searches todos. Reuse index view.

Note the difference in how params are sent.

### TPS - Why are get forms put in url query string?

**You Do**
Add a search form to the blog

## Nested Params

Demonstrate nested params. Why do we do this? Namespacing.

# Lesson Plan - Review Notes


Are learning objectives present and complete?
What is the ratio of talking vs. doing? (60/40, TT/ST-wg vs ST-sg / individual)
What is the level of engagement?
Are exercise plans present?
Any pitfalls with the exercises?
