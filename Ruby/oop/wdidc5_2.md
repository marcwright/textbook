Delivery Tips:

* Think about how long you're talking
* Move quicker sooner, slower later
* Cold Call more often
* Revisit LOs
* Defer questions when appropriate

# Ruby Objects

## Learning Objectives

- Explain what Classes and Objects are, and how they differ
- Write a class with an initialize method
- Write methods to define an interface to the class' behaviors
- Instantiate an object from a class and interact with it
- Write setter and getter methods
- Explain when and why you would use use attr_accessor
- Define class and instance methods and explain the difference between the two
- Explain the use of self in Ruby
- Explain the difference between local, instance and class variables


### Why use OOP? - Think Pair Share

Why use objects?

- Why use Objects and Classes?
  - Code reuse
  - Modularity / interoperability
  - Problem & Data modeling (translating a scenario into a solution)
  - Managing complexity
    - add a little formality up front so that things don't get too loosey-goosey
      later on

## Framing

- Our big concern is how do we structure our programs?
- Many paradigms - ruby is primarily object oriented.
- The idea is to define models for objects in our program, so we can use them
  as needed.

### Modeling in the Real World

- We can think about real world objects as having both state and behavior
  - a car
    - state (variables): on/off, speed, direction, color
    - behavior: accelerate, slow down, turn, honk
    - interface (methods): push_accelerator_pedal, push_brake_pedal, turn_wheel(deg),
      read_spedometer, read_speedometer, etc.
- think of another example together
  - point out the varying complexity
- Software is about modeling the real world - objects are a very intuitive way to do this.

## OOP Concepts

### Abstraction

Q: Think about methods, how are methods a form of abstraction?
A: they do something, but we don't care *how*.

Q: When we modeled our car a moment ago, did we discuss how we would write it?
Q: When we're using our objects, do we care how they were written (implemented)?
A: Most likely not!

Q: Why?
A: Consider this... do we care how a car works in the real world? No, as long as
   it has a consistent interface (pedals, speedometer, etc). Do you care whether
   it has a V6 or a V8, or disk breaks vs drum breaks?

### Encapsulation

Q: If all we care about is the interface, do we need to be able to look at the
   data the car uses internally? E.g., do you need to know how much fuel the car
   is sending to the engine at a given point in time? Should we be able to set
   those values?
A: No! That would break the abstraction!

The idea of preventing us from seeing and changing state directly is called
encapsulation.


### Objects

So to recap, objects:
- store their state in *variables*
- expose behavior through methods, known as the *interface*
- *encapsulate* implementation details for the purposes of abstraction

### Classes

- In ruby, we define object templates known as a `class`
- We create new objects from the class template using ClassName.new

## Code!

What are the objects in AMAco PDA?
- Person
- Task
- Temperature?

### Code Along Demo - Person Class for AMAco PDA

Ask the class to make suggestions for the class design.

What data?
  - name
  - age
  - favorite_food
What behaviors?
  - info

#### Topics to cover

- Write setter and getter methods
- Explain when and why you would use use attr_accessor
- Define class and instance methods and explain the difference between the two
- Explain the use of self in Ruby
- Explain the difference between local, instance and class variables


### An Aside - Pry

At this point, it's going to be tedious to interact / test our class. We're
going to use a tool called Pry to interact with our code.

Pry is two things:
- IRB on steroids
- A way to get a REPL in our program

    $ gem install pry

    # some code here
    binding.pry
    # you get a prompt here

### Pair Programming - Task Class for AMAco PDA

As a class, agree upon how we're going to model the class:

Data:
  - description
  - completed
Behaviors:
  - mark_complete

1. Write the class.
2. Stop and review solutions.
3. Integrate it into our AMAco PDA solution.
4. Stop and review.

### Adding Features to Person Class - Code Along

Let's update our person class:

Our person should have a mood. It should be either happy or tired. The info
method should include the mood. We can also sleep, work, or tell a joke. Working
makes a person tired, sleeping makes them happy, and they'll only tell a joke if
they are happy.

Don't worry about integrating with AMAco PDA yet.

What data?
  - mood
What methods?
  - info* (update)
  - sleep
  - work
  - tell_a_joke



# Lesson Plan - Review Notes

Are learning objectives present and complete?
What is the ratio of talking vs. doing? (60/40, TT/ST-wg vs ST-sg / individual)
What is the level of engagement?
Are exercise plans present?
Any pitfalls with the exercises?
