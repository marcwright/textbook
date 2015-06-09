## Objectives(SWBAT)

### Concepts
- explain why control flow is used in programming
- explain what conditionals are, and why we use them

### Mechanics
- Use boolean logic (&&, ||, !) to combine and manipulate boolean statements
- Use if, else, elsif statements to control logic flow in a Ruby program
- Use Ruby case statements

### Connection to Big Goal
Control Flow is foundational to computer programming

#### Framing
- Ask class what they think the purposes are for conditionals and loops/ mini discussion (5m)

## I do(conditionals/loops)
- creating and running a ruby program (5m)
	- create a simple hello world program through terminal
	- run program in terminal
- true vs false(5m)
	- also gloss over truthy and falsey
		- being a value is truthy
		- nil is falsey
- Draw truth tables for ! and && (2m)
	- true && true
	- true && false
	- !true
	- !false
- have students do TT for || (5m)
	- true || false
	- false || true
	- false || false
	- true || true
- demonstrate comparison operators inside IRB
	- ==
	- !=
	- <, <=
	- >, >=

- write and narrate through the following code (5m)
```

```

##### Practice exercise with conditional

- Have them write the code for the below.

```
puts 'Welcome to the club! How old are you?'
age = gets.chomp.to_i
if age > 20
  puts "Welcome to the club!"
elsif age > 75
  puts "You're welcome to come in, but I don't think this is the place for you..."
else
  puts "Hey kid! Get outta here!"
end

```
- why doesn't the elsif work with ages greater than 75?

rehash truthy falsey with below conditionals
```
if true
  puts "true is truthy, duh!"
else
  puts "true is falsey, wtf!"
end

if nil
  puts "nil is truthy"
else
  puts "nil is falsey"
end

if 0
  puts "0 is truthy"
else
  puts "0 is falsey"
end
```

Another way to do conditionals is utilizing case statements

```
puts "How many pieces of pizza can you eat??"
pizza_slice_count = gets.chomp.to_i
case pizza_slice_count
when 0
	puts "Oh, you must not like pizza"
when 1
	puts "Oh, you must not be very hungry"
when 2
	puts "2 pieces eh?"
when 3
  puts "Thats a good amount of pizza!"
else
	puts "we're going to have to order more pizza"
 end
```

- write and narrate through the following code(10m)
```
i = 0
while i < 10
  puts i
end
```

- Ask class why its looping infinitely and how we can fix it.(3m)
- insert a break into loop
- switch while with an until loop(2m)

##### Practice Exercise with loops

## Make a temperature converter(30m)
- demo converter and personal assistant command

AMAco keeps up with the trends, and we know that 'retro' is the latest fad among today's youth. AMAco needs a CLI based temperature converter!

- Create a ruby program that asks the user for input

- It should convert the input from celsius to fahrenheit and then puts that value.

- ask the user what the starting temperature is(fahrenheit or celsius)

- output should be opposite of starting temperature type

- add Kelvin to the program as well!

- Using loops, start making a personal assistant commandline app that has the temperature converter as an option in its interface

- *BONUS* have your personal assistant app do something besides converting temperature!


#### References
	[http://code.tutsplus.com/tutorials/ruby-for-newbies-conditional-statements-and-loops--net-16537](http://code.tutsplus.com/tutorials/ruby-for-newbies-conditional-statements-and-loops--net-16537)
