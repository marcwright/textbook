## Software is not created in one inspired moment.

-- Refactoring: Ruby Edition

Note:

Lesson is based on Ruby Rogues podcast #178 and "Refactoring: Ruby Edition" book.
Fields, Jay; Harvie, Shane; Fowler, Martin; Beck, Kent (2009-10-15). Refactoring: Ruby Edition (Addison-Wesley Professional Ruby Series) (Kindle Location 164). Pearson Education. Kindle Edition.

---

## Objectives

- Describe refactoring
- Share why (and when) we should refactor
- Perform some common refactorings
- Be intolerant of code smells

---

## What is Refactoring?

> Making very, very small changes
> that **don't** affect the overall behavior of your system.

Note:

---

## Define: (noun)
(5:19)

> A change made to the internal structure of software
> to make it easier to understand
> and cheaper to modify
> without changing its observable behavior.


---

## Define: (verb)

> restructure software
> by applying a series of refactorings
> without changing its observable behavior

Note:

Pause at Avdi, "wait, wait, wait"

---

# Refactoring Example:
## Extract Method

> to turn part of a larger method into a new method. By breaking down code in smaller pieces, it is more easily understandable. This is also applicable to functions.

http://en.wikipedia.org/wiki/Code_refactoring

---

## I Do: Remember this code from WMATA?

``` ruby
lines = wmata[:red_line]  # array of stops on the line
lines.each do |line|
  puts line
end

...

lines = wmata[:blue_line]  # array of stops on the line
lines.each do |line|
  puts line
end
```

Note:

Obvious duplication

---

# [Extract Method](https://refactoring.guru/extract-method)

Note:

Copy to file.  Run.  Show output.
Prompt for suggestions.

ONLY `def display_stops`

---

## We Do

- Clean up, rename
- Header
- Short format

Note:

AND long format

---

1. [Extract Method](https://refactoring.guru/extract-method)
1. [Rename Method](https://refactoring.guru/rename-method)
1. [Extract Variable](https://refactoring.guru/extract-variable)
1. [Inline Variable](https://refactoring.guru/inline-temp)

see: wmata_lines_solution.rb

---

# You Do: Rafactor This To Improve Clarity (10 min)

## Follow the refactoring steps as closely as you can.

## Refactor monthly_report_starter.rb

``` ruby
# monthly_report.rb
def print_report(title, for_month, data)
  # header
  puts "Report: #{title}"
  puts "  for #{for_month}"
  puts "--------------------------"
  # body
  puts data
  # footer
  puts "--------------------------"
  puts "Printed: #{Time.now}"
end

print_report("WDI Instructors", "03/2015", ["Adam", "Matt", "Andy"])
```

Note:

Framing:  
- We're not just looking for duplication.  We also want to add clarity.
- Review this code.  What can you extract to improve clarity?
- Try to follow the refactoring steps exactly.

---

## Steps?

https://refactoring.guru/extract-method

---

## After Refactoring

``` ruby
def print_report(title, for_month, data)
  print_header(title, for_month)
  puts data
  print_footer
end

def print_header(title, for_month)
  puts "Report: #{title}"
  puts "  for #{for_month}"
  puts "--------------------------"
end

def print_footer
  puts "--------------------------"
  puts "Printed: #{Time.now}"
end

print_report("WDI Instructors", "03/2015", ["Adam", "Matt", "Andy"])
```

---

## When?

# Refactor ***All*** the Time

> Little bits of improvement
~
> to keep it healthy

Note:

Healthy is a good analogy.

---

Refactoring vs. Restructuring
(7:04-8:50)

---

## How has this refactoring practice affected your coding practice?
(16:36)

- Dramatic reduction in size of methods
> "A method that has 3 statements is getting a bit long."
- Treating things as immutable whenever possible

---

# Why Refactor?

---

# Speed

> The whole point of refactoring is to go faster.

---

# healthy == FAST!

---

## coding is like running
## then
## we are running a marathon

---

# When Should We Refactor?

---

## Code Smells

> If it stinks, change it.

Grandma Beck, discussing child-rearing philosophy

Note:

Fields, Jay; Harvie, Shane; Fowler, Martin; Beck, Kent (2009-10-15). Refactoring: Ruby Edition (Addison-Wesley Professional Ruby Series) (Kindle Locations 1032-1033). Pearson Education. Kindle Edition.

---

## Code Smells

> Very **easy** to spot thing
> That *usually* implies a problem

### Examples:
- Duplication
- Too big
    - Long Methods, Large Class, Long Parameter List
- Scattered knowledge
    - Divergent Change, Shotgun Surgery, Feature Envy
- Data Class
- Comments

Note:

Divergent Change: changes in many ways
Shotgun: one change affects many places
Feature Envy: more interested in another class than itself

---

# Comments...
## a code smell?
(29:10)

> Comments are a deoderant
> Covering up a bad smell.

## The goal

Make the comment irrelevant, by
*showing* the intention in the code

Note:
It's a *smell*.  Comments *may* be necessary.

---

## Benefits of
## Identifying and Defining
## Code Smells?

Note:

YouDo

---

## Benefits of
## Identifying and Defining
## Code Smells

- conversation
- empowered
- practice

---

## Identifying Code Smells
(25:25)

> Important skill... **identifying** "code smells".
> And learning to become **intolerant** of them
> That will drive the desire
> You've got to keep wacking these smells.

Note:

If you can identify, then you can work with someone else to solve.

---

## Code Smells

# Duplication
## or
# Obfuscation

---

## Naming:
(34:00)

> indicate the role, which are indicative of their duck type

- using a name which indicate type is a smell
- consistent conventions:
    - user_count vs. count_user vs. num_users

---

# Practice?

## Identify places for Refactoring (Code Smells)
## Keep Refactoring!

Note:

Code smells(35:00)

---

## Step 1

> When you get the understanding in your head,

> move that understanding out of your head

>   and get it into the code

## Code should reflect your intention

---

## Software is not created in one inspired moment.

Note:

Understanding that software development is a constant activity and not a static event helps us to remember that code can and should be organic.

Book info:
Fields, Jay; Harvie, Shane; Fowler, Martin; Beck, Kent (2009-10-15). Refactoring: Ruby Edition (Addison-Wesley Professional Ruby Series) (Kindle Locations 167-168). Pearson Education. Kindle Edition.

---

## Two hats

- adding functionality
- refactoring

---

## Refactoring

- Identifying code smells
- Changing the code without affecting functionality
- Continually

---

# This is a LOT of change

---

# Beauty,
# Elegance, and
# Correctness
# Come with iterations

---

> Small is smooth

> Smooth is fast

---

## What is waste?

- use the highway?
- it's ok to explore and experiment

Note:

I need to get on the other side of the woods.
Do I push through the woods, or go way out of my way on the highway?

Sometimes we don't know until we explore and experiment

---

# YOU MUST
## Explore
## and
## Experiment

---

# [Ruby Rogues #178](http://devchat.tv/ruby-rogues/178-rr-book-club-refactoring-ruby-with-martin-fowler)

## Book Club: Refactoring Ruby w/ Martin Fowler

Note:

- Based on "Refactoring" by Martin Folwer in 1999
- Concept has a lot of support
- But... not practiced widely
- My Opinion: Given short shrift

---

## Other topics covered

- Expectations
- Git
- Technical Debt
- Polite Legacy Codebase
- Getting people to embrace refactoring
- How to be a polite legacy codebase
- Tradeoffs of Microservices

---

## Expectations
(1:00:19)

- It's a continual process
- One Year Later

Note:

You don't know what the design should really be until a year later

---

## What is Refactoring?

> Making very, very small changes
> that **don't** affect the overall behavior of your system.


Note:

What would you have to do trust your changes?

---

## Refactoring

> Making very, very small changes
> that **don't** affect the overall behavior of your system.

~
> So that your tests always pass.

> So that you are always ready to deploy

Note:

What if you had a full battery of automated specifications that checked to see if the software did what was expected?

---

## Forward motion

- measure your progress by adding tests
- AND getting the tests to work.

---

# Which Leads Us Too...

---

<h2 style='color: red'>Red</h1>
<h2 style='color: green'>Green</h1>
## Refactor

---

# Extra Stuff

Note:

Given enough time.


---

## Know What You Are Talking About
(42:30)

- If it's important, learn it

---

## Getting People to Embrace Refactoring
(43:35)

- cultivating understanding
- beauty, elegance, and correctness comes with iterations

Note:

---

## Git Commits
(36:35)

> If your editor isn't open when you are committing #yourdoingitwrong

- link to the commit on github


---

## A Refactoring Browser

> I find I refactor more (20:30)

- it feels like less work
- changes are small
- I feel more brave about changing

---

## RubyMine (Practice)

---

# Practice
(25:25)
- focus on one code smell per week


---

Tech Debt
(54:11)

- interest accrues
- concept understood by devs, managers, and executives

---

## What else has changed over the last 20 years?
(40:07)

- the concepts from Extreme Programming
    - refactoring
    - continuous integration and delivery
