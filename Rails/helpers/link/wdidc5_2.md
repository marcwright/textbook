Delivery Tips:

* Think about how long you're talking
* Move quicker sooner, slower later
* Cold Call more often
* Revisit LOs
* Defer questions when appropriate

# Rails Form Helpers

## Learning Objectives

* Implement namespaced params in a form and explain the advantages
* Use `strong_params` to limit what attributes can be modified
* Generate forms for an AR model objet using `form_for` helpers
* Explain the use of an authenticity token in Rails forms
* Generate non-model forms using `form_tag`

## Outline

### HTML Forms

#### Whip Around (8 minutes)

Everyone write 5 facts about HTML forms (3 minutes). Go around the room until people can't
give me any more.

5 minutes to share back / collect.

### Namespaced Params

** I DO **

Demonstrate how we can modify the existing forms to namespace params. (Artists)

Why do this?
* Group related data (no conflicts)
* Clean up our controller

### Strong Params

What's different about `Artist.update(params[:artist])`?
We don't control which data gets passed in.

Demonstrate adding a method `artist_params` to controller.

** YOU DO **

Update Songs to match.

### form_for

** I DO **

There's starting to be a lot of duplication and 'boilerplate' in our form.
Wouldn't it be nice if we could abstract that?

Demonstrate porting artists to `form_for`.

What's important here?

** You do **
Port songs to use form_for.

### form_tag

** I do **

Demonstrate creating a form_tag for a search form.

** You do **




# Lesson Plan - Review Notes

Are learning objectives present and complete?
What is the ratio of talking vs. doing? (60/40, TT/ST-wg vs ST-sg / individual)
What is the level of engagement?
Are exercise plans present?
Any pitfalls with the exercises?
