Delivery Tips:

* Think about how long you're talking
* Move quicker sooner, slower later
* Cold Call more often
* Revisit LOs
* Defer questions when appropriate

# Intro to Active Record

## Learning Objectives

* Explain what an ORM is and why ORMs are useful
* Explain convention-over-configuration, and how it relates to ActiveRecord
* Utilize ActiveRecord to perform CRUD actions on a database
  * create
  * save
  * all
  * find, find_by
  * where
  * update
  * destroy

## Outline

### ORMs and ActiveRecord - 15 min

We now have ways to persist data into a database, but we need a way to
get that data into our Ruby programs. We could use a gem called 'pg',
which lets us issue SQL commands from ruby, and parse the results.

But in reality, most of the time, we'll be better off with an ORM.

Basics of ORMs:
* They 'map' (translate) objects to rows in our DB (and vice versa)
* 1 table per Model/Class/Entity
  * table name is model name pluralized
  * each column is an attribute for that model
  * models inherit from ActiveRecord::Base (explain inheritance)
* Handles data types / conversion
* Handles associations using foreign keys (Monday)


### Code Along ActiveRecord CRUD - 45 min

* Share starter code
* `bundle install`
 * discuss dependencies
* Walk through app.rb
* Create `Author` class
  * Note it's empty except for inheritance
* Fire up app.rb and play with Authors
  * DON'T DELETE AUTHORS!
  * .all
  * .find
  * .where
  * .create
  * .destroy (on created author ONLY)
* EXERCISE
  * Find all authors born in the USA
  * Find a specific author by name
  * Create a new author
  * Update their birth_year
  * Destroy them

#### Re-group and discuss

What do we think of AR? What issues do we have?

### Extra time? Books

Exercise: Create Book model and play with it.


# Lesson Plan - Review Notes

Are learning objectives present and complete?
What is the ratio of talking vs. doing? (60/40, TT/ST-wg vs ST-sg / individual)
What is the level of engagement?
Are exercise plans present?
Any pitfalls with the exercises?
