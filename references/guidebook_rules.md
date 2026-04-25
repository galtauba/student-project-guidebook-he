# Guidebook Rules

Write in Hebrew.

The final product is a single HTML teaching guide.

---

# Teaching Mode

The guide must feel like a private lesson.

It should teach the student how the system works, not merely document file contents.

Prefer clarity, teaching order, and full context.

---

# Full Code Requirement

Include all relevant source code files in the HTML.

For important files, do not only list them.
Actually walk through them.

---

# Conceptual Walkthrough Format (CRITICAL)

For each important file:

1. show the file name
2. explain the file purpose
3. split the file into logical code units
4. for each logical unit:
   - give it a clear title
   - explain why this unit exists
   - show the real code snippet of that unit
   - explain how the unit works
   - explain the connection to the previous and next unit

Do not separate the explanation from the code.

---

# Explain by Meaningful Blocks

Do NOT explain code by blind line counting.

Group together lines that belong to one coherent purpose.

Examples:
- checking whether a user already exists in the database
- validating submitted form fields
- building a list of selected items
- checking inventory shortages
- updating approval status
- returning items to inventory
- preparing a template context
- checking permissions before an action

Each such group must be explained as one full logical idea.

---

# Avoid Overly Large Blocks

Do not keep giant blocks that contain several different ideas.

If one section contains multiple distinct teaching ideas, split it.

Examples of good splitting:
- registration field extraction
- registration validation
- duplicate username check
- saving the new user
- login password verification
- building selected_items
- shortage detection
- inserting the order
- inserting order items
- approval shortage loop
- inventory reduction
- creating a team action block

This is especially important in large files such as:
- backend controller files
- monolithic route files
- service files with many branches

---

# Route Breakdown Rule

Do not explain a large route as one single unit if it contains several internal stages.

Break routes into their real internal logic.

Examples:

For `register`, use units such as:
- reading form fields
- validation
- duplicate username check
- insert user
- success flow

For `login`, use units such as:
- reading login fields
- fetching user
- password verification
- approval verification
- session creation

For `new_order`, use units such as:
- role check
- blocked team check
- loading actions/items
- building selected_items
- validating quantities
- shortage detection
- insert into orders
- insert into order_items

For `reject_return`, use units such as:
- reading reject form values
- validating reason_type
- validating blocked_action_id
- loading action and team context
- restoring returned items to inventory
- creating/updating team_action_blocks
- updating return status

If a route still feels large, split again.

---

# Multi-Responsibility Rule

A logical unit should usually have one main responsibility.

If a unit does several of these together, it is probably too large:
- read input
- validate input
- query data
- decide between several branches
- write to DB
- render or redirect

When that happens, split the unit.

---

# No Truncated Code in Units

Every logical unit must show complete real code for that unit.

Do NOT use:
- `...`
- abbreviated route bodies
- shortened placeholder examples
- partial unit code that hides the meaningful lines

If the code is too large, split the unit again into smaller units.

Never solve length problems by hiding code.

---

# Code-Specific Explanation Rule

Explanations must be specific to the actual code shown.

Bad explanation:
- "this is the main logic of the section"
- "this block processes data"
- "the system prepares the next step"

Good explanation:
- "here the system checks whether the username already exists in the users table"
- "here the loop builds selected_items only for quantities greater than zero"
- "here shortages are collected instead of failing immediately so all missing items can be shown together"
- "here the inventory is reduced only after the order is approved"

Every explanation must refer to the actual meaning of the code in front of the student.

---

# Deep Explanation Rule

Do not stop at naming the block.

Inside the explanation, clarify:
- why this block is needed
- what exact decision it makes
- what exact query or update happens
- why the order of operations matters
- what business consequence follows from success or failure

Example:
Instead of only saying "this block checks shortages",
also explain:
- how the shortages list is built
- why the system collects all shortage messages together
- why rejection happens before any DB insert into order_items
- what the user sees if shortages exist

The student should understand the reasoning, not just the label.

---

# When to Drill Down Further

Inside a logical block, go deeper only when necessary.

Go deeper when the code contains:
- important conditionals
- loops with business meaning
- validation rules
- security checks
- database updates
- key calculations
- state transitions
- branching decisions such as approve/reject

In such cases, explain the critical inner lines or decisions, but still keep the explanation organized around the full logical unit.

---

# Block Explanation Template

For each logical unit, explain:

## Title
A meaningful title, not just “Block 1”.

## Purpose
What the block is trying to achieve.

## Context
What happened before this block, and why the code reaches it.

## Real Code
Show the actual code snippet for this logical unit.

## How It Works
Explain the internal steps clearly and specifically.

## Input
What data the block depends on.

## Output / Side Effect
What the block returns, saves, updates, or causes.

## Failure Meaning
What would happen if this block were removed, broken, or bypassed.

## Connection Forward
What the next logical unit depends on from this block.

---

# No Line-Range-Only Explanations

Do not explain code using only references like:
- lines 1-44
- lines 220-280

Line ranges may appear as optional secondary metadata, but never as a substitute for showing the real code.

The actual code snippet must appear directly in the explanation.

---

# No Repetitive Template Language

Do not repeat generic explanation patterns across many blocks.

Avoid repeated boilerplate phrases such as:
- "before this block..."
- "inside this block..."
- "after this block..."

unless they are rewritten in a way that is genuinely specific to the exact code.

If many blocks end up sounding the same, the explanations are too generic.

The student must feel that each block was read and understood individually.

---

# Templates and UI Files

For templates and UI-related files, explain:
- what screen this file represents
- who uses this screen
- what data arrives into the screen
- what forms/actions exist in it
- what routes or handlers those actions connect to
- what the student should notice in the structure

Break important templates into logical units too, such as:
- page shell
- head and stylesheet inclusion
- top navigation
- flash messages
- main form
- submit button area
- result table
- conditional warning area
- repeated row block
- footer area

Do not reduce templates to one-line summaries.

Important templates must not stop at one generic unit if the file has multiple clear parts.

---

# Template Granularity Rule

For templates, do not stop at:
- "file structure"
- "form area"
- "screen content"

if the file clearly has more meaningful parts.

Examples:
- `base.html` should usually be broken into head, navigation, flash area, content block, footer
- `login.html` should usually be broken into page shell, form, fields, submit button
- `register.html` should usually be broken into identity fields, role selector, team selector, submit button
- `admin_returns.html` should usually be broken into returns table, approve action, reject form, block action selector

The explanation should match what the user actually sees and does on the screen.

---

# CSS and Styling Files

For CSS files, explain:
- what visual role the file has
- major style sections
- layout strategy
- important selectors and why they matter
- reusable style patterns
- responsive or desktop layout decisions if relevant

Break CSS into logical units too, such as:
- root variables
- base/body styles
- layout shell
- navigation/sidebar styles
- cards/tables/forms
- code blocks
- desktop layout rules

Do not reduce CSS to one short paragraph.

Large CSS files must have several logical units.

---

# CSS Granularity Rule

Large CSS files must be split into real teaching units.

Do not use one generic unit like:
- "the style file"

Split into meaningful parts such as:
- color system and variables
- body and page background
- container and topbar layout
- card and grid system
- forms and buttons
- status badges and tables
- responsive or print behavior

Each of these should be navigable from the sidebar when relevant.

---

# README / requirements / config files

These files may be simpler, but still explain them with context.

Do not produce repetitive generic explanations like:
- "this line is documentation"
- "this file is used for configuration"

Instead explain the real meaning of the file in this project.

For short files, 1 useful unit may be enough.
For longer files such as README, split into meaningful sections when possible.

---

# Embedded Structure Rule

Inside the final HTML:
- every file must be a distinct section
- every logical code unit must be a subsection
- every subsection must be reachable from the sidebar
- code and explanation must appear together

This rule applies to:
- backend files
- templates
- CSS
- JavaScript
- important config files

---

# Sidebar Depth Rule

The sidebar must not stop at file names.

For every important file, include nested navigation links to the logical code units inside that file.

Examples:
- file: app.py
  - unit: duplicate username check
  - unit: password validation
  - unit: selected_items building
  - unit: shortage detection
  - unit: approve order
  - unit: reject return and create block

- file: templates/login.html
  - unit: page shell
  - unit: login form
  - unit: username input
  - unit: password input
  - unit: submit button

- file: static/style.css
  - unit: root variables
  - unit: body/base styling
  - unit: layout shell
  - unit: sidebar styling
  - unit: card/table styling

---

# Desktop HTML Layout Expectations

The HTML should be optimized for desktop reading:
- sticky sidebar
- wide content column
- large readable code blocks
- clear visual hierarchy
- easy long-form reading

---

# Critical Rule

Never do this:
- explanation here
- full code dump far away somewhere else

Instead do this:
- explain a logical unit
- show its code immediately
- continue to the next logical unit

---

# No Duplicate Source Dump Rule

Do not create a second large “full source” section if the same code has already been shown unit-by-unit in the walkthrough.

The walkthrough is the main source-learning section.

A small appendix or source index is acceptable only if it adds genuine value and does not duplicate the whole learning experience.