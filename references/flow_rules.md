# Flow Detection Rules

Detect the important flows of the project dynamically.

Do not hardcode flow types.

---

## What counts as a flow

A flow is a meaningful end-to-end behavior in the system.

Examples:
- user registration
- login
- creating an order
- approving an order
- reporting a return
- API request handling
- CLI command execution
- game update loop
- rendering a page
- saving a record
- processing uploaded data

---

## For each important flow, identify

1. entry point
2. files involved
3. logical code units involved
4. major decisions and conditions
5. data movement
6. output/result

---

## Flow Explanation Style

Explain flows in human terms.

Good explanation:
- what starts the flow
- what checks happen first
- what data is collected
- what decisions are made
- what gets stored or returned
- what the user sees next

Avoid vague flow descriptions.

---

## Relationship to Code Walkthrough

The flow explanations should support the later code explanations.

That means:
- top-level flow section gives the big picture
- file/code-unit sections give the detailed implementation