# Enumerables

## Learning Objectives

- explain enumeration in ruby and how it relates to loops
- explain the difference between each and map
- use enumerables on ruby collections

In programming we come across this programming paradigm of looping through collections... often. So ruby contributors mades our lives alot easier by including the enumerable module.

If you understand loops and arrays and hashes, there's nothing new conceptually here. But you'll learn to do more with prettier, fewer lines of code.

```
numbers = [1,2,3,4,5,6,7,8,9]

numbers.each do |number|
  puts number
end

# functionally equivalent to above code
numbers.each{|number| puts number}

```

Some Important Enumerables
- each
- map
- each_with_index
- select
