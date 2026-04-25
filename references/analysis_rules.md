# Project Analysis Rules

Analyze the project before writing the HTML.

---

## 1. Detect Project Type

Detect the actual type of project, for example:
- web app
- backend/API
- CLI
- game
- library
- script
- desktop app

Do not assume a framework or language in advance.

---

## 2. Detect Structure

Detect whether the project is:
- single-file
- multi-file
- monolithic
- modular
- layered

---

## 3. Detect Important Components

Identify important components such as:
- UI / frontend
- backend logic
- database layer
- API communication
- configuration
- templates
- styling
- scripts
- services
- models
- helpers
- event handling
- state management

---

## 4. Detect Important Files

Identify which files are important for understanding the project.

Important files usually include files that contain:
- startup
- routing
- rendering
- business logic
- database access
- security
- validation
- state changes
- external integrations
- user interactions

---

## 5. Detect Logical Code Units

Inside each important file, detect meaningful logical units.

Examples:
- import/setup block
- config block
- DB connection block
- user existence check
- permission check
- validation block
- data transformation block
- loop building a result list
- approval/rejection decision block
- rendering block
- error handling block

The final explanation must use these units rather than blind line slices.

---

## 6. Detect Flow Connections

Detect how files and logical units connect.

Examples:
- form → route → validation → DB → response
- click → handler → update state → render
- command → parse args → run logic → print result

---

## 7. Detect Excludable Files

Files that are usually not useful to embed as source explanation:
- binary database files
- compiled artifacts
- caches
- dependency folders
- generated lock noise if not educationally useful

If a file is excluded, its role may still be explained briefly if needed.