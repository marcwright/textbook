# Enumerables

## Learning Objectives
### Concepts
- explain enumeration in ruby and how it relates to loops
- explain the difference between each and map

### Mechanics
- use enumerables on ruby collections


#### Opening Framing & Hook
PKI (review) use cases for loops (~5m) WE DO
- prod for the use case for loops in arrays if students aren't listing that one.

In programming we come across this programming paradigm of looping through collections... often. So ruby contributors mades our lives alot easier by including the enumerable module.

If you understand loops and arrays and hashes, there's nothing new conceptually here. But you'll learn to do more with prettier, fewer lines of code.

Do a small review of a simple loop through an array (~ 10m) I DO
- looping through an array
- do numbers in order, ask questions about just `puts i` instead of `puts numbers[i]`
```
numbers_in_order = [1,2,3,4,5,6,7,8,9]
numbers_out_of_order = [9,5,6,8,7,4,2,3,1,]

i = 1
while i < numbers.length
  puts i
  i += 1
end
```

We do this kind of thing alot, maybe its not as simple as just printing a number to the computer, but we use collections alot and we iterate over them, alot.

Do the same thing functionally with an each method (~ 10m) I DO

```
numbers.each do |number|
  puts number
end

numbers.each{|number| puts number}
```

Show map method:

```
numbers.map do |number|
  puts number
end
```

Have a variable point to both enumerables and point out differences in outputs and the similarities of the input and side effects.

### Do class exercise YOU DO (~ 15m)

Fist to five on the differences between map and each, especially with regard to input, output, and side effects.

### BREAK

### Doc Dive (~20m) YOU DO
[http://ruby-doc.org/core-2.2.1/Enumerable.html#method-i-sort_by](http://ruby-doc.org/core-2.2.1/Enumerable.html#method-i-sort_by)
Break into groups of 4 or 5
- each_with_index
- find_all
- inject
- sort_by
- all?
- any?
- one?
- max
- max_by
- min_by

## In class exercise- Titleizer!
