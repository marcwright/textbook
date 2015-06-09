Delivery Tips:

* Think about how long you're talking
* Move quicker sooner, slower later
* Cold Call more often
* Revisit LOs
* Defer questions when appropriate

# Methods

## Learning Objectives

* Explain why methods are useful in the context of
  * DRY code
  * Readability
  * Modularity
  * Flexibility and extensibility
* Write and call a simple Ruby method
* Write and call a Ruby method that accepts input arguments
* Write and call a Ruby method, making use of the method's return value
* Define scope in the context of programming
* Describe the rules of variable scope in Ruby

## Outline

* We've already seen a lot of methods in Ruby so far
* What are some characteristics of those methods?
  * Accepted some information
  * Gave us back some information
  * Acted on objects
* The difference between defining a method and calling a method
  * With Ruby methods, this confusion is mitigated, as Ruby-folk are the definers
  * With our own methods, this line can get blurred

### Codealong - Writing Methods

* Create a file called `welcome.rb`
* WAM (write a method) to print a welcoming message
* WAM to print a personalized welcoming message to a particular person


### Exercise - Role Play Methods (15 minutes)

Ask for 4 volunteers.
Write a ```find_tallest``` method on the board, that takes 3 args, p1, p2, p3.
Demonstrate passing in 3 people, and how the method works when it is called.
What happens if method shaves their head while comparing?
Emphasize return values vs fact that I still have references to all arguments.

### Scope (10 minutes)

* Explore scope. What exists where? From where can I access what things?
* Establish that input and output arguments are the only ways in and out of a method
* Demonstrate that arguments are passed by reference - `.upcase!()`
  * Diagram out what happened

```ruby
favorite_language = "ruby"
def yell(text)
  puts "yelling:"
  puts text.upcase!
  puts "whew!"
end
yell(favorite_language)
puts favorite_language #note it's changed, we want to avoid this usually
```


### Exercise 1 - How to tell a joke in 8 easy steps.

For every method below, write the method and use (a.k.a 'call') the method 2x (with different arguments).

Additionally, note / explain:
  * What input does this method take?
  * What does this method return?
  * What side effects does this method have?

1. Write a method that displays a joke to the user (you pick the joke).
  * (This method should have 1 line in the body.)

2. Modify the method so that it still displays the joke, but this time returns the string "joke told!" as well.
  * (2 lines)

3. Modify the method so that you can give it any joke (a parameter), which it will show to the user instead of the original joke.
  * (2 lines)

4. Modify the method so that, after displaying the joke, it takes user input from the terminal and stores it in a variable.
  * (Continue to return 'joke told!').

** Paws **

5. Modify the method so that it returns the user input.

6. Modify the method so that if the user input is "I don't know" it displays a snarky comment, otherwise, it says "you got my joke!"
  * continue to return the user input

** Paws **

7. Modify the method so that it returns true or false. It should return false if the user said 'I don't know", true otherwise.
  * continue to display snarky comment, "you got my joke"

8. Modify the method such that you can give it a 'correct response' to expect from the user. The method should behave as above, only now return true if the input matches the correct response, false otherwise.

** Paws **

9. Write a new method called "tell_two_jokes". It should call our original method, and take 4 arguments, joke1, answer1, joke2, answer2.

# Lesson Plan - Review Notes

Are learning objectives present and complete?
What is the ratio of talking vs. doing? (60/40, TT/ST-wg vs ST-sg / individual)
What is the level of engagement?
Are exercise plans present?
Any pitfalls with the exercises?
