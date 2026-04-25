---
name: student-project-guidebook-he
description: Generate one complete Hebrew HTML guidebook for any software project, including full source code, logical code explanations, desktop-only structured navigation, and oral exam preparation questions.
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
- interview preparation questions
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
4. detect files and logical code units
5. plan the teaching structure
6. generate the final HTML
7. generate oral exam questions inside the HTML

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
- updating approval status
- rendering a template
- handling permission checks
- returning items to inventory

Each logical block must be explained as a complete unit.

Only zoom into specific lines when the internal logic is important enough to require it.

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

# Sidebar Navigation Rule (CRITICAL)

The final HTML must include a desktop sidebar navigation with nested links.

The sidebar must link to:
- major top-level sections
- each file section
- each logical code unit inside each important file

Each file and each logical unit must have a unique HTML id anchor.

The user must be able to quickly jump to:
- a file
- a specific explained code block inside that file

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

You may still avoid breaking on medium screens, but the design target is desktop use only.

---

# Interview Questions Rule

The final HTML must include a substantial oral-exam preparation section.

Generate 30-50 open-ended questions.

Do NOT generate:
- multiple choice questions
- ready-made answers as the default study mode

Questions should prepare the student for a 1-on-1 oral exam with a teacher.

Each question should preferably include:
- category
- the question itself
- points the student should cover

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