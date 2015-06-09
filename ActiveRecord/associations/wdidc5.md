# Active Record Associations

## Learning Objectives
### Concepts
- explain the purpose of associations in ActiveRecord (AR)
- how they make common operations simpler
- how they make it easier to code once associations are established

### Mechanics
- use the common AR helper methods to manage associations (CRUD)
  - belongs_to
    - .author     - returns the associated author object
    - .author =   - sets the associated author object
    - .create_author  
  - has_many
    - .books      - returns the list of associated books objects
    - .books =    - overwrites the list of associated books
    - .books <<   - adds to the associated list of books
    - .books.create  - creates a new book associated with the author called on
- explain the purpose of `dependent: destroy`

## Opening Framing

We've seen the power of AR record in terms of writing SQL for us (providing a
better  interface to the DB). As we saw on Fri, that power extendeds to  
expressing / managing relationships (i.e. the ones in our ERDs). Every program
we'll ever write has relationships between models/entities.

Object Composition - objects made out of / associated with other objects
(car/engine or trainer/pokemon example)

Associations are just a way to represent relationships between different objects
in code.

### Think-Pair-Share

**Given what we know about how AR worked with single objects, what feature do
you think AR should / would provide for associations?**

Write student responses on the board.

Expected answers:
- declare the nature of the relationships between entities (models) (1:1, many-many)
- get asssociated objects
- modify (add /remove associations)
- create objects based on associations

Write the list of commons methods given by AR to manage associations and define
each one.

## AR Association Features

## I do- lecture (10m)

Let's take facebook for example:
- What do you think the code looks like for a user creating a post on facebook?
  - do you think it queries the database for a user or user_id then creates a post passing in those parameters?
  - wouldn't it be nice if programmatically, a post is created like we think of it in english?
  - Wouldn't it also be nice, if there was a quick method or function we could use to access all of a user's posts, comments, photos, friends, messages, likes

Associations allow us to do just that. Once we define a relationship in code, like an association in Active Record, it streamlines and makes these CRUD actions much more efficient.

## We do- Codealong (~45 m)
### creating and loading schema.sql(review 10m)
Let's hop into some code. Let's start by creating a schema file. We should all be familiar with this. Lets create a file called `tek_schema.sql` Let's write in it:(quick refresher on schema.sql)

```sql
DROP TABLE IF EXISTS instructors;
DROP TABLE IF EXISTS students;

CREATE TABLE instructors(
  id SERIAL PRIMARY KEY,
  name VARCHAR(50) NOT NULL,
  email VARCHAR(50) NOT NULL
);

CREATE TABLE students(
  id SERIAL PRIMARY KEY,
  name VARCHAR(50) NOT NULL,
  email VARCHAR(50) NOT NULL,
  instructor_id INTEGER NOT NULL
);
```

Lets go ahead and create our database `createdb tek_db` and load our schema in `psql -d tek_db < tek_schema.sql`

### app.rb file (AR basics review 10m)
*Note* I'm going to keep all of the class definitions in the main app.rb file. In the future you want to separate these definitions into other files and then `require_relative`. For the purposes of this lesson I'm going to consolidate into one file so you can see the associations in the class definitions all at once.

```ruby
require 'active_record'
require 'pg'
require 'pry'

ActiveRecord::Base.establish_connection(
  database: 'tek_db',
  adapter: 'postgresql'
)

class Instructor < ActiveRecord::Base
end

class Student < ActiveRecord::Base
end

binding.pry
```

Lets go ahead and create some records(have schema file open and pry open side by side):
- create an instructor in pry, have students walk you through `Instructor.create({name})`
- create 2-3 students under instructor.
  - adam = Instructor.first
  - Student.create({name: "Jocelyn", email: "jocelyn@email.com", instructor_id: adam.id})
  - Student.create({name: "John", email: "john@email.com", instructor_id: adam.id})
  - attempt to do `adam.students`
  - close out of pry to update `app.rb`
### HAS MANY (10m)
- add `has_many :students` association to instructor and `belongs_to :instructor` to student
- do `adam.students` again in pry. ooooohhhh ahhhhhh
- exit pry take away a `has_many` or `belongs_to` to show what each is doing
- do adam.students.create({name: "Noah", email: "noah@email.com"})
- briefly explain how to create seed file?

```ruby
require_relative 'lib/instructor'
require_relative 'lib/student'

Instructor.destroy_all
Student.destroy_all

instructors = Instructor.create([
  {name: "Adam", email: "adam@email.com"},
  {name: "Matt", email: "matt@email.com"},
  {name: "Andy", email: "andy@email.com"}
])

students = Student.create([
  # {name: "Jocelyn", email: "jocelyn@email.com", instructor_id: instructors[0].id},
  # {name: "Don", email: "don@email.com", instructor_id: instructors[1].id},
  # {name: "Phil", email: "phil@email.com", instructor_id: instructors[2].id}
])

```



## Break 10m

## You do- Doctors and patients.(30 m)

## I Do- show my hopsital solution to introduce many-to-many association

### HAS MANY- THROUGH

- show schema file first, explain how appointments works and how it allows the many to many relationship
- show active record `app.rb` file
- go into pry and show:
  - `doctor.patients`
  - `doctor.patients`
  - `doctor.skills << skill`
  - `patient.doctors`
  - `patient.appointments`
  - `doctor.appointments`
  - `patient.doctors[0].skills`
  - `skill.doctor =`

  Push Code up so they can do next exercise

## You Do- Refactor the We do codealong for TEK (45m)
