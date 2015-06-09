Toss pics into slack
Collaborative notes
whiteboard (dont' write too low)


# Intro to Git (Local Repositories)

## Learning Objectives
### Concepts

- Explain what version control is and why developers use it
- List the main components of a git repository and how they relate:
  - repo
  - index
  - working tree
  - commit

### Mechanics

- Initialize a local git repository
- Add and commit changes to a git repository
- Checkout an old version of a file.

## Outline

Ideally, this lesson will come after students have built their first program.

### Think-Pair-Share - What is the purpose of version control? (10 minutes)

Question:
Think about how you've managed tracking changes to a file over time (perhaps
with other people).
**What problems did we face?**
**How might a VCS solve these?**

Possible points students might bring up:

- Reverting to past versions
- Keeping track of what each version 'meant'
- Comparing changes to past versions
- Sharing changes
- Collaborating / discussing changes
- Fearlessness in making changes

### Core Concepts of Git Repositories (40 minutes)

**I DO** (20 minutes)

Have students watch as instructor initializes an existing project as a
repository, adds files, and makes the first commit.

Instructor should use the whiteboard to diagram the parts of git involved (repo,
working tree, index, commits).

* Terms
  * **repository** - collection of commits (save points of the working tree)
  * **working tree** - the folder (and it's files and sub-folders, that are in the repository)
  * **commit** - a snapshot of the working tree at a giving time (along with a message of what changed)
  * **the index** - a staging area where we list changes we want to commit
  * **branch** - a label on a commit (it's the ancestry of the commit that constitutes what we usually consider the 'branch')
  * **tag** - also a label for a commit, but it never changes
  * **master** / development - conventional names for branches
  * **HEAD** - what is currently checked out.

#### Exercise (15 minutes)

1. Initialize our current class project (AMAda) as a repo
2. Make an initial commit
3. Make a small change
4. Commit that change
5. Revert back to (checkout) the original version of your code
6. Switch back to (checkout) your latest version
