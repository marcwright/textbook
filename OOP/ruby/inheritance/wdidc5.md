Delivery Tips:

* Think about how long you're talking
* Move quicker sooner, slower later
* Cold Call more often
* Revisit LOs
* Defer questions when appropriate

# TITLE

## Learning Objectives

* Explain the use of inheritance in OOP
  * Extend the functionality of an existing class
  * Extract commonalities into a parent class
* Explain the lookup chain wrt Ruby inheritance
* Construct a parent and two children classes that utilize
  * added attributes and methods in the children classes
  * overriding methods
  * super

## Outline

**Talk about it**

* Inheritance is when one class "inherits" a bunch of behavior from another, and adds functionality on top.
* Terms: Parent class, Child class
* Why would we want to do this?
  * Extend an existing class
    * Special character vs normal character in a video game
  * Extract commonality
    * Yesterday's GoT homework

### Basic syntax and playground

**We do**

* Car
  * horsepower - a number between 1 and the limits of your imagination
  * fuel - number between 0 and 5
  * rev() - return the string "VROOOM!"
  * drive() - decrement fuel by 1 and return true if fuel > 0, else return false
* PoliceCar
  * arsenal - array of strings representing weapons, initialized to empty array
  * add_to_arsenal(weapon)
* DeLorean
  * current_time - a number representing a year
  * time_travel(year) - change current_time to 'year' if it's positive

### Exercise

**You do**

* Pet
  * name - string
  * owner - string, owner's name
  * age - number
  * foods_eaten - initialized to empty array
  * love_owner() - return a string proclaiming love towards owner
  * eat(food) - push 'food' into the foods_eaten array
  * list_foods() - return a string containing all the eaten foods
* Dog
  * ear_type - A string (Eg. "Floopy", "Upright", "Stubby", "Shaggy")
  * bark() - Returns a string with a bark in it (eg. "Woof woof")
* Cat
  * hours_slept - initialized to 0
  * sleep() - increments hours_slept by 1
  * judge_person(person) - Accepts a string 'person' and returns a judgmental string about that person

### Overriding methods and super

**We do**

* Cat#love_person
* Initialize methods

### The Lookup Chain

**I do**

* Whiteboard the lookup chain in the pets context

### EXERCISE TBD



# Lesson Plan - Review Notes

Are learning objectives present and complete?
What is the ratio of talking vs. doing? (60/40, TT/ST-wg vs ST-sg / individual)
What is the level of engagement?
Are exercise plans present?
Any pitfalls with the exercises?  
