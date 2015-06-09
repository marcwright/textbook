# BDD: Behavior Driven Development

---

# Quick Review: 3 Lessons

1. **Build** on what is known
1. Care about **where** you are
1. I control it.  By telling it **precisely** what I want.

---

## Learning Objectives
- Live and breath the BDD Mantra
- List benefits of BDD/TDD
- Create simple specs using rspec
- Set up and write RSpec tests using
  - `describe`
  - `before(:each)`, `before(:all)`
  - `let`
  - `expect`
  - `to` and `not_to`
  - `eql`, `eq`, `be`

---

## BDD: Behavior Driven Development

> Having **live** documentation

~

> that specifies the **behavior** of a system.

Note:

Live Documentation: documentation that **must** change when the code changes

Prompt: What do you think happens to documentation today, as code changes quickly?

---

## BDD: What?

A failing spec

**drives**

the creation of code

  to answer that spec.

Note:

- If the spec changes, the new spec will fal, forcing a change in code.
- If the code changes, it will fail a spec

---

## BDD: How?

- Write a failing, runnable specification before changing any code.
- Run a suite of automated tests after every change

---

### New bug?  

- Write the _specifications_ which identify what the program should be doing.
- See that spec _fail_.
- Write the _code_ to fix it.
- _Review_  your changes for clarity.

---

- See that spec fail (**red**).
- Write the code to fix it (**green**).
- Review your changes for clarity (**refactor**).

---

### New feature?

Same steps.

- Red (failing spec),
- Green (write code to pass)
- Refactor (make it better)

---

### Change a feature?

Same steps.

Red, Green, Refactor

Note:

Maybe you are starting to see a pattern

---

## Our Mantra...

<h1 style='color: red'>Red</h1>
<h1 style='color: green'>Green</h1>
# Refactor

---

# Let's Feel It

## Exercise 1, [TestFirst.org/learn_ruby](http://testfirst.org/learn_ruby)

- follow instructions closely
- small steps
- failing spec, _then_ code to pass

- follow instructions _closely_

Note:

(10 min)

---

## BDD: Behavior Driven Development

Having **live** documentation

that specifies

the **behavior** of a system.

---

## T&T: Why?

- Why runnable specs?
- Why Red, then Green, then Refactor?  Is that order important?
- Why focus on behavior of system, instead of
  - object state, or
  - ensuring objects reflect problem domain
  -

Note:

- Write on board
"Let's watch for these things as we go through the lesson"

- What is the behavior of the system.

---

## BDD/TDD

- Test First
- TDD
- BDD

Note:

(5 min)

Behavior Driven vs. Test Driven
Essentially the same, yet not.

---

[Sapir-Whorf](http://en.wikipedia.org/wiki/Linguistic_relativity)

> a language affects the ways in which its respective speakers conceptualize their world

## ~

Or, more simply...

> language determines thought

---

Together, we decided that...

while you _could_ do the right thing when thinking about Tests,

Thinking in terms of **Behavior**

usually **leads** you in the right direction.

Note:

---

## That said...

# Do BDD
## or
# Do TDD
##~
## Just make sure you...
# [TATFT](https://google.com?q=TATFT)

---

# State of the Union

- Documentation was failing us (it still is)
- Procedural vs. OOP
- SRP

Note:

Draw Procedural Box vs. Collection of Objects interacting.
- Emphasize switch from flow to interaction.


---

## Why?

- Live Docs (Trust)
- Safety Net (Trust)
- Better Design (Focus, Reusable)
- Speed (Focus, Rhythm)

---

# Speed?

Note:

Speed? Really?  I'm writing twice as much code.
All these other things are nice, but what we really want is speed.

Compare manual testing
New login page
  Add "remember me"
  Add "forgot my password"

Compare time for repeated manual testing vs. fast, automated testing.

---

## Speed?

- Writing code *as fast as possible* isn’t necessarily the goal.  
- We want **maintainable** code that answers our need.  

> I see tests as a Limiter, forcing your code to *earn* its place.

---

## Speed

> Small is smooth
> Smooth is fast

~

<small>Ruby Rogues Episode #178, "Refactoring, Ruby Edition"</small>

Note:


---

## Focus

- **forces** us to think think about **use**
- We only write enough code to make the test pass.


Note:

"forces": There's that that ecosystem leading us in the right direction again.

YAGNI

Use:
1. What does it have to do?  
1. What would I like the code to look like?
1. What does it depend on?

---

## Design

- History (Test First -> TDD -> BDD)
- The specs guide you
- Let go of your hubris
- Often fulfill the requirement earlier then expected (in a better place)

---

## Better Design? Why?

- The spec, or test, is the first user of your code.
- If your code is hard to test, that means it's hard to _use_.

~

> Do you think it might be good to know this early?

Note:

Discuss
 - testing in isolation, minimizing dependencies.  (refer to diagram)
 - Respond to the pain.
 - OutsideIn

---

## Rhythm

- Red, Green, Refactor.
- Tiny steps
- Forward motion
- Often done before you realize it.

Note:

Create tests many times in one hour

---

# I Do: Ordinal

```
  1 #=>   1st
  2 #=>   2nd
 23 #=>  23rd
115 #=> 115th
```

Note:

Start with Pseudo Code
I could keep writing pseudo code, that I might delete later... OR
I could write documentation that lives on.

passed_number = ARGV[0]

rspec: describe, it

Do I *really* do it this small?
Change speed for terrain

---

## Rhythm

- Red, Green, Refactor.
- Small steps
- Forward motion
- Often done before you realize it.

---

# Atom.io: Auto Indent

- Open Preferences (Cmd+,)
- Click link: "your keymap file"
- Paste in:
```
'atom-workspace atom-text-editor:not([mini])':
  'cmd-i': 'editor:auto-indent'
```

---

# You Do: Scrabble Scorer
Setup:
```
$ gem install rspec
$ atom ~/.rspec
```

Add these lines:
```
--color
--format documentation
```

---

# You Do: Scrabble Scorer

To run specs:
```
$ rspec
# or
$ rspec spec/bdd_scrabble_scorer_spec.rb
```

To run your scorer:
```
ruby bdd_scrabble_scorer.rb quirky #=> 22
```

---

## Common arguments

> “Tests require me to know what I want.  Sometimes I don’t know what I want my code to do, so I just have to play with it a little."

That sounds reasonable.  Almost.

Note:

My reply: _“How can you write code if you don't know what it is supposed to do?  Do you just type randomly until something works?"_

---

## Advice for now

- Keep it small
- Write some specs, sometimes
- <span style='color: red'>Red</span>, <span style='color: green'>Green</span>, (don't forget the) Refactor
- Respond to the pain

Note:

Write the obvious specs

---

## Exercises 2-4 in [testfirst.org/learn_ruby](http://testfirst.org/learn_ruby)

Remember:  

  - Test First
  - Comment out all the specs
  - Move forward one step at a time.

---

## Review pokearena specs

Note:

Introduce `let`, `context`

---

## Resources

- Videos, now
  - Jim Weirich: [Roman Numerals Kata via TDD](https://www.youtube.com/watch?v=983zk0eqYLY)
  - For you music lovers: [Has anybody seen my code?](https://www.youtube.com/watch?v=vKrr7aXUc1E)
- Books, now
  - [Extreme Programming Explained, Kent Beck](http://www.amazon.com/Extreme-Programming-Explained-Embrace-Edition/dp/0321278658)
- Books, later
  - POODiR (Practical Object Oriented Development in Ruby), Sandi Metz
  - Rails 4 Test Prescriptions, Noel Rappin

Note:

Quiz Questions:

- What is the last step of the BDD?  List one reason for this step.
  - Red, Green, **Refactor**.  Maintainability,
-
