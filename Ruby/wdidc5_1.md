## Objectives(SWBAT)

### Concepts
- describe the utility of computer programming
- define the role of a REPL in programming
- list 5 common data types used in ruby and their uses
- differentiate between statements and expressions
- describe what variables are and what they are used for
- explain the concepts of mutability and immutability
- describe what a method is and why they are useful
- differentiate between input, output and side effects for methods
- explain what a type error is

### Mechanics
- use REPL to evaluate ruby code
- create and run a ruby program

### Connection to Big Goal
Establish a foundation of the ruby language. It'll be the premise that is used to build a toolset for web development.

### Opening Framing & Hook

Prior Knowledge Inventory(5m)
-	list every day uses of computer programming
- turn and talk(3m)
	- *what did the programmer think about in order to write the program for email*
	- probe about data types
- what things are made more effective through programming
Metaphor of PB&J making robot(5m)
- computer programming allows us to do simple tasks efficiently
Bringing us back to ruby basics. To learn the building blocks of your first computer programming language.

## I do (ruby basics)
- Use Prior Knowledge Inventory to extrapolate information about data types from the student. (5m)
- explain REPL and show uses(narrate 17m)
	- gem install pry
- speak to result with respect to statements in ruby

- List potential data types(2m)
	- list data types(objects)
		- in the next couple of weeks, we'll be talking alot about objects. all you need to know for now is:
			- objects have data/info
			- objects have methods
	- similar things to do for each datatype
		- class
		- docs
		- show example methods
	- strings
	- floats
	- integers(FIXNUM)
	- booleans
	- symbols (immutable lightweight string, tend to use them as labels, or options)
	- nil

- use variables within REPL, question students while exploring about mutability and assignment(narrate 10m)
	- ask why we use variables?
	- set variable name = "andy"
	- set variable to a = "something"
	- set variable to the_number_ten = 10
	- speak briefly about naming convention and semantic naming
		- what are some things about this variable name that is good?
		- "" is bad?
		- going forward we want to name things semantically, but not the extreme as the above example
		- do full_name in REPL, than draw diagram(variables/value chart)
			- first_name + last_name = full_name

### We do
- guided practice with REPL(15 m)

- Instruct students to experiment with pry and random methods they've come across.
	- documentation scavenger hunt
		- first, speak to how to generally read documentation
		- direct them to ruby strings docs for materials to use
		- break into 4 groups to look up methods in groups then share findings to class
			string, count, gsub, split, to_i, center, lstrip
			fixnum, %, abs, to_s, fdiv, to_f, even?
		- (pick some methods for students to look up) || (find 3 methods on data types we learned and write down a summary of them)
		- walk around class to observe progress(10m)

- Draw and show diagram for I/O/side effects in a method(5m)
	- show input output and side effects for
	- string.upcase
	- puts
	- gsub (inputs are both the object being called on and arguments)
  - fist to five
  	- who is confident they can differentiate between return values(output) and side effects

#### Mutability
- what does mutability mean?
- can I change something without changing the assignment?
```
my_name = "andy"
your_name = "andy"
my_name.object_id
your_name.object_id

name = "bob"
another_name = name
name.upcase!
another_name

symbol = :new_symbol
symbol.upcase
symbol.upcase! # talk about i/o/side effects

```

### break(10m)


## We do(ruby basics)


- run through the first 5 exercises as a class together from assignment-exercise.md


## You do(ruby basics)
- whiteboard rest of problems in groups, don't allow students to input anything into computers.(10m)
- discuss findings and go over groups problems(5m)

## I do
Lets create a ruby program!
Ok, so first thing, touch the file to create it
Do hello world program in ruby then run in terminal.


### break(10m)


## Closing
- Summarize learning objectives
- Prod students about what they think about what arrays and hashes are.

#### References
[http://ruby-doc.org//core-2.2.0/String.html](http://ruby-doc.org//core-2.2.0/String.html)<br>
[http://ruby-doc.org//core-2.2.0/Fixnum.html](http://ruby-doc.org//core-2.2.0/Fixnum.html)<br>
[Chris Pine's Book](https://pine.fm/LearnToProgram/)

conditionals and loops for tuesday

domain and problem modeling
ERD's
database

SQL
