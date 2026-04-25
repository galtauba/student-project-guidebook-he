---
name: student-project-guidebook-he
description: Generate one complete Hebrew HTML guidebook for any software project, including full source code, deep logical code explanations, desktop-only hierarchical navigation, and oral exam preparation questions.
---

# Core Goal

Transform ANY software project into ONE complete Hebrew HTML guidebook.

The final HTML must include:
- project overview
- architecture explanation
- flow explanation
- full source code of the project
- explanation of the code by meaningful logical units
- embedded code snippets inside each conceptual explanation
- file-by-file walkthrough
- oral exam preparation questions
- desktop-only hierarchical navigation

---

# Final Output Rule (CRITICAL)

You must output ONLY ONE final deliverable:

- student_guidebook.html

Do NOT generate:
- analysis markdown files
- planning files
- question markdown files
- coverage markdown files
- any additional deliverables

All analysis must be internal and all final content must be embedded into the single HTML file.

---

# Internal Pipeline (INTERNAL ONLY)

Internally perform these stages:

1. analyze the project
2. detect architecture and project type
3. detect important flows
4. detect important files
5. detect logical code units inside files
6. split oversized logical units into smaller teaching units
7. plan the teaching structure
8. generate the final HTML
9. generate oral exam questions inside the HTML

Do NOT output these internal stages as separate files.

---

# Universal Adaptation Rule

Never assume a specific project type.

Always detect and adapt to the actual project.

Possible project types include:
- web application
- backend/API
- CLI tool
- desktop application
- game
- library/SDK
- script-based project
- modular project
- monolithic project
- layered architecture

The explanation style must adapt accordingly.

---

# Full Source Rule (CRITICAL)

The final HTML must include ALL relevant project source files.

This includes, when present:
- code files
- templates
- CSS files
- JavaScript files
- config files
- README and dependency files when useful for understanding

Do not replace source code with summaries.

Do not omit source files unless they are clearly generated artifacts, binaries, or irrelevant external dependency files.

---

# No Truncated Code Rule (CRITICAL)

Inside the conceptual walkthrough sections, do NOT use:
- `...`
- shortened placeholder snippets
- partial code that hides the main logic
- summarized pseudocode instead of the real project code

Every logical unit must show the real code of that unit in a complete and honest way.

If a logical unit is too large, split it into smaller logical units.
Do not hide part of the code.

---

# Logical Explanation Rule (CRITICAL)

Do NOT explain code by blind line-by-line narration.

Instead:
- detect meaningful logical code units
- group related lines into one coherent teaching block
- explain each block as one full idea

Examples of logical code units:
- checking whether a user exists in the database
- validating form input
- opening a database connection
- building a selected items list
- checking shortages
- rendering a template
- handling permission checks
- returning items to inventory

Each logical block must be explained as a complete unit.

Only zoom into specific lines when the internal logic is important enough to require it.

---

# Granularity Rule (CRITICAL)

Do not keep very large units if they contain multiple distinct ideas.

If a section contains several meaningful sub-flows, split it into smaller logical units.

Examples:

Instead of one large unit like:
- "user screens"

split into smaller units such as:
- dashboard data preparation
- blocked action lookup
- building selected_items
- checking shortages
- creating the order record
- saving order items
- validating a return
- calculating missing items

Instead of one large unit like:
- "admin screens"

split into smaller units such as:
- listing pending orders
- approving an order
- rejecting an order
- approving a return
- rejecting a return and creating a block
- adding inventory items
- updating inventory items
- adding teams
- deleting teams

Instead of one large unit like:
- "template structure"

split into smaller units such as:
- page shell
- top navigation
- flash messages
- main form
- submit action
- table display
- conditional warning area

A logical unit should represent one coherent teaching idea.

---

# Route Splitting Rule (CRITICAL)

Do NOT keep a full route as one teaching unit if it contains multiple distinct steps.

Large routes must be split into their real internal stages.

Examples:

Instead of one large unit like:
- `register`

split into:
- reading form fields
- basic validation
- duplicate username check
- inserting the new user
- handling success and redirect

Instead of one large unit like:
- `login`

split into:
- reading username and password
- fetching the user from the database
- password hash verification
- approval check
- session creation and redirect

Instead of one large unit like:
- `new_order`

split into:
- role and block checks
- loading actions and inventory
- building selected_items
- validating quantities
- shortage detection
- inserting the order row
- inserting order_items rows
- success redirect

Instead of one large unit like:
- `reject_return`

split into:
- validating reason_type
- validating blocked_action_id
- loading order/team/action context
- determining the rejection reason
- restoring returned items to inventory
- creating/updating the team_action_blocks record
- updating the returns status

This rule applies especially to:
- Flask routes
- controller actions
- request handlers
- large functions with several DB operations

---

# Multi-Decision Rule (CRITICAL)

If a unit contains:
- more than one major conditional branch
- more than one loop with different purposes
- more than one distinct database write
- more than one business decision

then the unit is probably too large and must be split again.

Do not keep large mixed-purpose blocks just because they are inside one function.

---

# Code-Specific Explanation Rule (CRITICAL)

Explanations must be tailored to the actual code.

Do NOT use generic repeated phrases such as:
- "this is the place where the main logic happens"
- "before this block the system builds the previous stage"
- "after this block the routes receive a ready result"

Every block explanation must directly reference:
- the real purpose of this exact block
- the exact checks being performed
- the exact data being queried, built, validated, updated, or returned
- the exact business meaning of the code

The explanation must feel specific to the code, not templated.

---

# Deep Explanation Rule (CRITICAL)

Inside each logical unit, explain more than the headline.

You must explain:
- why this code exists
- what exact condition or rule it enforces
- what data it reads
- what data it writes or changes
- why the developer chose this sequence
- what would happen if this code failed or was removed
- what next step depends on it

Do not stop at "what this block does".
Also explain the reasoning and consequences inside the flow.

---

# Embedded Code Rule (CRITICAL)

Inside the conceptual walkthrough sections, always embed the actual code snippet of the logical unit directly inside the explanation.

Do NOT explain using only:
- line ranges
- vague summaries
- references to “the code above”

The student must see:
1. the block title
2. the block explanation
3. the actual code snippet for that block
4. the explanation of how that code works

The code and the explanation must appear together in the same place.

---

# Context Rule (CRITICAL)

Always explain:
- what happened before the block
- what this block is trying to achieve
- what happens inside the block
- what happens after the block

The student must understand the role of the code in the full flow, not only the isolated syntax.

However, keep this context specific to the real code and flow.
Do not use repetitive template language.

---

# File Walkthrough Rule

For every important file:
- create a dedicated section
- explain the file purpose
- break the file into logical code units
- show the real code for each logical unit
- explain how the units connect together

Do not keep all explanation in one place and all code in another place.

Explanation and code must stay close together.

---

# Minimum Unit Depth Rule (CRITICAL)

Do not leave important files with only one generic subsection.

For important files, create multiple logical units whenever the file contains multiple ideas.

Guideline:
- simple files: at least 1–2 logical units
- medium templates/forms: at least 2–4 logical units
- large backend/controller files: at least 5–12 logical units, or more if needed

This rule applies especially to:
- app/controller/server files
- shared templates such as base.html
- complex form templates
- large CSS files

---

# Template and CSS Depth Rule (CRITICAL)

Do not stop at a single generic subsection for templates or CSS files when they clearly contain several meaningful parts.

Examples:

`templates/base.html` should usually be split into:
- head and CSS include
- top navigation
- flash messages
- content block
- footer

`templates/login.html` should usually be split into:
- outer card or page shell
- form tag
- username field
- password field
- submit button

`templates/new_order.html` should usually be split into:
- action selector
- blocked actions warning area
- items table
- quantity inputs
- submit button

`static/style.css` should usually be split into:
- root variables
- base/body styles
- layout shell
- topbar/nav
- cards and grids
- forms and buttons
- status pills / tables / lists
- responsive or desktop adjustments

If the file has several clear parts, the sidebar and the explanation must reflect those parts.

---

# Navigation Rule (CRITICAL)

The final HTML must include a desktop sidebar navigation with nested links.

The sidebar must link to:
- major top-level sections
- each file section
- each logical code unit inside each important file

This rule applies not only to the main backend file, but also to:
- templates
- CSS files
- JavaScript files
- other important source files

Each file and each logical unit must have a unique HTML id anchor.

The user must be able to quickly jump to:
- a file
- a specific explained code block inside that file

---

# Sidebar Depth Rule (CRITICAL)

The sidebar must not stop at file names.

For every important file, include nested navigation links to the logical units inside that file.

This means:
- backend files need block-level navigation
- templates need block-level navigation
- CSS files need block-level navigation
- shared layout files need block-level navigation
- larger config or documentation files may also need block-level navigation if they contain multiple meaningful sections

Do not use one generic nested item like:
- "file structure and its relation to flow"

when the file clearly contains several real teaching units.

---

# Desktop-Only Layout Rule (CRITICAL)

The final HTML is intended for desktop screens only.

Optimize for desktop:
- sticky or fixed sidebar
- wide readable content area
- large code blocks
- nested navigation
- no need for mobile-first behavior
- no need to collapse everything into a narrow single-column mobile layout

You may still avoid breaking badly on medium screens, but the design target is desktop use only.

---

# No Separate Full Source Section Rule (CRITICAL)

Do NOT create a large separate section that dumps the full source code again after the walkthrough.

The walkthrough itself must already contain the real code, unit by unit.

A short appendix or source index is acceptable if truly useful, but it must not duplicate the main educational content.

The main learning experience must be:
- explanation
- code
- explanation
- next code unit

not:
- explanation section
- then later a giant repeated source dump

---

# Interview Questions Rule (CRITICAL)

The final HTML must include a substantial oral-exam preparation section.

Generate 30-50 open-ended questions.

Do NOT generate:
- multiple choice questions
- short trivia questions
- ready-made answers as the default study mode

Questions should prepare the student for a 1-on-1 oral exam with a teacher.

Each question should include:
- category
- the question itself
- points the student should cover

Questions must be distributed across:
- overview
- architecture
- flows
- file roles
- code logic
- debugging
- design decisions
- future improvements

---

# HTML Must Include

The final HTML must include, in a clear structure:

1. overview
2. architecture
3. data model if relevant
4. major flows
5. file-by-file walkthrough
6. logical code-unit walkthrough with embedded code
7. oral exam preparation questions
8. final summary

---

# Writing Style

Write in Hebrew.
Write clearly and pedagogically.
Assume the student may not fully understand the code yet.
Prefer teaching clarity over brevity.