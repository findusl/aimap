# Specification as source

Use the written specification as the source of truth. AI agents implement the specification, and automated tests verify that the application follows it.

- `1_features/` defines how the system behaves through use cases. Use the [write-use-cases skill](.agents/skills/write-use-cases/SKILL.md) when writing or editing them.
- `2_frontend-design/` defines how the frontend looks and how users and browser tests interact with it. Start with the [UI contract](2_frontend-design/ui-contract.md).
- `3_technical-tweaks/` defines implementation constraints and adjustments where specified. Its scope is limited to implementation. Feature behavior and frontend appearance remain governed by their respective specifications.

When intended behavior or appearance changes, or its specification is missing or ambiguous, update the relevant specification before changing the implementation. When the implementation diverges from a clear specification, fix the implementation and add regression coverage where needed.

Keep test case specifications in `4_test-cases/`. Use automated acceptance tests to verify specified behavior across normal workflows, edge cases, and failures. Use realistic mailbox scenarios for behavior that depends on the IMAP server or other mail clients.
