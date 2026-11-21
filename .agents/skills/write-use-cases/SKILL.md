---
name: write-use-cases
description: Write or revise user-goal use cases in AIMAP's 1_features/ directory.
---

# Write use cases

Write one use case per user goal. Give an independently useful goal its own case, such as testing a connection from either Add or Edit. Keep choices that serve the same goal together, such as a filtering rule's conditions and actions.

Describe what the user can do and observe. For example, the sorting use case says new mail is handled immediately. The technical specification explains how the service detects its arrival.

Use a short, action-oriented title and a stable three-digit ID. For example, use `UC 100 — Add an IMAP server` as the title and `uc-100-add-imap-server.md` as the filename. Use `1xx` for connections, `2xx` for filtering rules, and `00x` for ungrouped cases. Space IDs in the connection and rule ranges by tens where possible, using the gaps for related additions. Preserve IDs when editing or renaming cases.

- **Triggers** is optional. An actor is a person or external system that participates. A trigger is the event that starts the flow. For example, the mail server is an actor and new mail arriving is a trigger. List triggers before the main flow when several events start it or an automatic start needs explanation. If the first step already makes the trigger clear, state it there once.
- **Main flow** gives the shortest sequence of user actions and system responses needed to reach the goal. Refer to inputs collectively. A step like “The system validates the input” is enough when the rules define validation.
- **Business rules** specify the inputs, defaults, validation criteria, and conditions for actions such as saving. Keep field names and field-specific requirements here, before the alternative flows.
- **Alternative flows** describe what happens when the main flow branches, including what the system reports and how the user can proceed.

Give each requirement one home. The flow says when a check happens. The rules say what makes it pass. When an input changes, update its rule and touch the flow only if the sequence or outcome changes.

When one use case starts another, link to it at that step. Describe the resulting behavior in the use case that carries it out.

When moving or renumbering a use case, check that its title, filename, and incoming references agree, including links to specific headings.

Record undecided behavior in [open-questions.md](../../../open-questions.md). Once a decision is made, update the use case that owns it and remove the resolved question.
