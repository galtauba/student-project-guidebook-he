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
Explain the internal steps clearly.

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

# Templates and UI Files

For templates and UI-related files, explain:
- what screen this file represents
- who uses this screen
- what data arrives into the screen
- what forms/actions exist in it
- what routes or handlers those actions connect to
- what the student should notice in the structure

For CSS files, explain:
- what visual role the file has
- major style sections
- layout strategy
- important selectors and why they matter

Do not reduce templates/CSS to one-line summaries.

---

# README / requirements / config files

These files may be simpler, but still explain them with context.

Do not produce repetitive generic explanations like:
- “this line is documentation”
- “this file is used for configuration”

Instead explain the real meaning of the file in this project.

---

# Embedded Structure Rule

Inside the final HTML:
- every file must be a distinct section
- every logical code unit must be a subsection
- every subsection must be reachable from the sidebar
- code and explanation must appear together

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