Delivery Tips:

* Think about how long you're talking
* Move quicker sooner, slower later
* Cold Call more often
* Revisit LOs
* Defer questions when appropriate

# Relationships in SQL

## Learning Objectives
- Explain how to represent one-to-one and one-to-many relationships in a SQL DB
- Explain what a foreign key constraint is and why you would use one
- Explain what a join is and when you would use one

## Outline

### Begin with a Review

Review high-level aspects of DBs:
  * DBs let us store and query data
  * like spreadsheets - tables and columns
  * table names are plural
  * columns have a name, type, and constraints
  * indexes give us speed when querying (book index example)
  * CRUD - INS, SEL, UPD, DES

### One-to-many

Consider/discuss a one-to-many relationship: books and authors.
* Given a book, I want to list author name and status.
* Given an author, I want to list all her books.

#### Option 1 - Duplicate Info (Wrong)

**authors**
- name
- nationality (active/inactive)

**books**
- title
- pub_date
- author_name****
- author_nationality****

**Downside**: duplication, keeping data in sync.

#### Option 2 - Array of IDs (Wrong)

**authors**
- name
- nationality
- book_ids****

**books**
- title
- pub_date

**Downside**: Parsing list, can't index (for speed!)

#### Option 3 (Correct!)

**authors**
- name
- nationality

**books**
- title
- pub_date
- author_id


### Joins

Whiteboard for students how joining works using foreign keys.

## Writing SQL

Instructor demos:
```sql
SELECT id FROM authors where name = 'J.K. Rowling';
SELECT * FROM books where author_id = 2;

SELECT * FROM books JOIN authors ON books.author_id = authors.id;
SELECT * FROM books JOIN authors ON books.author_id = authors.id WHERE authors.nationality = 'United States of America';
```

### EXERCISE: Books/Authors (One to Many)

See prompt.md in ex_library

## Many-to-Many Relationships

Diagram a simple many-to-many relationship and explain the join table.

Ask students to come up with an example of a many-to-many relationship. An example might be topics / categories to books.

Instructor demos creating categories table in schema, and adding 2 categories and writing queries on them with books. Note that we won't be using these in the HW, we'll let rails take care of them.

## EXERCISE / HW: Apartment Building

See labs_homework/d04_hamco_realty_2/prompt.md

# Lesson Plan - Review Notes

Are learning objectives present and complete?
What is the ratio of talking vs. doing? (60/40, TT/ST-wg vs ST-sg / individual)
What is the level of engagement?
Are exercise plans present?
Any pitfalls with the exercises?
