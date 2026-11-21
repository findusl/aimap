# Project vision

Keep existing mailboxes organized automatically. A server-hosted application will sort email in place, so people can keep their mail provider and see messages in the right folders in the mail clients they already use.

Users define what belongs where. Fixed rules handle conditions users can state directly. Language models can make bounded decisions where the meaning of a message matters. A model can answer several rule questions about the same message without requiring a conversation.

## Product goals

- Connect to existing IMAP mailboxes across providers.
- Fetch messages automatically.
- Sort messages using a sequence of fixed or LLM-assisted rules.
- Let rules stop processing or allow later rules to run.
- Save sorting changes to the mailbox so they appear in other mail clients.
- Handle changes from other mail clients safely, including when a message is deleted during sorting.
