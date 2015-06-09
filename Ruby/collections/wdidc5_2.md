Delivery Tips:

* Think about how long you're talking
* Move quicker sooner, slower later
* Cold Call more often
* Revisit LOs
* Defer questions when appropriate

# Collections and Enumeration

## Learning Objectives

#### Concepts

* Explain the difference between an array and a hash and when you would use each

#### Mechanics

* Create an array, access items in an array, modify items in an array
* Add and remove elements from an array
* Create a hash, access items in a hash, modify items in a hash
* Add and remove elements from a hash
* Use built in Ruby methods to enumerate over a collection
	* each
	* select

## Outline

### Arrays

#### I-do

##RUN THROUGH!!!
How would we write a list of names?
##END RUN THROUGH!!!

**Why can't we use a bunch of variables?**

* Create a variable for a number
* Create more variables for more numbers
* What if:
  * the user determines how many numbers I need?
  * the user determines which variable to access?
* Enter arrays

**Array Basics**

* Declare an array [10, 20, 30, 40, 50]
* Access elements num_array[0], num_array[1]
* num_array.first, num_array.last
* num_array.length

**Adding and removing elements**

* Push and pop
* Shuttle, <<

* Show arrays of strings
* Show mixed arrays

**Doc Dive**

* Pair doc dive - [Ruby docs](ruby-doc.org/core-2.1.0/Array.html)
* Lefts check sample and flatten
* Rights check shuffle and uniq
* Teach your partner, and we will ask you to explain your partner's methods

#### You-do

**1. Lap times**

Timmy is running laps! Let's use an array to keep track of his lap times. Open up irb for this exercise.

* Create an empty array called `lap_times` to store Timmy's lap times
* Timmy's first lap was 53 seconds. Make your array reflect this using `push`
* Timmy's second lap was 59 seconds. Make your array reflect this using `push`
* Timmy's third lap was 52 seconds. Make your array reflect this using `push`
* It turns out Timmy had already run a lap of 55 seconds before we got to the field. Make your array reflect this using `unshift`
* Timmy's last lap (the 52-seconds one) was disqualified because of excessive tail wind. Remove it from the array using `pop`

Great! We've got Timmy's lap times. Now, access the array you've created to find the following information.

* How many legal laps did Timmy run?
* What is the lap time of Timmy's second lap?
* What is the lap time of Timmy's third lap?
* What is the lap time of Timmy's first lap?
* What is the lap time of Timmy's last lap?

### Enumeration

#### PORT THIS PROGRAM TO CODE NOW

**I do**

I want to print all of Timmy's lap times one after the other. I need to access these values one at a time and do something with each one. With **each** one.

I want to make a new array with milliseconds. I need to **map** my first array to another one.

### Exercise

**We do**

Let's use our newfound knowledge of arrays to add a to-do list to HAMda.

* When the user selects the 'Task Manager' option in the main menu, they should be directed to a sub-menu with the following info
  * A list of all tasks
  * 'Add task' option
  * 'Finish task' option
  * Prompt for user input
* Selecting 'Add task' should prompt the user to enter text for a new task, add it to the existing list of tasks, and redirect to the main menu
* Selecting 'Finish task' should prompt the user to enter the task number, remove the corresponding task, and redirect to the main menu
* Bonus: After performing task manager operations, the user should be redirected to the task manager menu instead of the main menu

### Hashes

* Personal info example
* KEY-VALUE PAIRS
* The key is the "locator" for each element
* Example of the web (Rails)!

#### We-do

* Create a personal info hash
  * name
  * age
  * occupation
  * favorite_food
* Things to cover in this process
  * Creating a hash
  * Syntax of a hash
  * Adding key-value pairs
  * Accessing values through keys

### Exercise

Let's add our personal information to HAMda.

* Step 1 - Add our personal info
  * Instantiate a hash with your personal info in it at the beginning of our program
  * Add an option in our menu to view our personal info.
  * When the user selects this option, the program should print our personal info and redirect to the main menu

Here's an example of what we should see.

```
Name: Adam
Age: 50
Occupation: Co-Founder, AMAco Enterprises Global
Favorite Food: Burritos
```

* Step 2 - Add an option in the main menu for the user to edit their personal info
  * When the user selects this option, the personal info should be displayed
  * The user should then be prompted to enter which piece of info they wish to edit
  * The user should then be prompted to enter the new value for the piece of info they selected
  * The new personal info should then be displayed and the user should then be redirected to the main menu

# Lesson Plan - Review Notes

Are learning objectives present and complete?
What is the ratio of talking vs. doing? (60/40, TT/ST-wg vs ST-sg / individual)
What is the level of engagement?
Are exercise plans present?
Any pitfalls with the exercises?
