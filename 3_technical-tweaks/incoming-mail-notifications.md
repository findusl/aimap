# Incoming mail notifications

For [UC 009 — Sort incoming email](../1_features/uc-009-sort-incoming-email.md#timing), select the standard IMAP mailbox `INBOX`. Use IMAP IDLE on the open connection to receive notifications and trigger retrieval of new mail. [Mailbox naming](https://www.rfc-editor.org/rfc/rfc9051.html#section-5.1) · [IDLE](https://www.rfc-editor.org/rfc/rfc9051.html#section-6.3.13)

## Recognizing messages after reconnecting

For [resumed sorting](../1_features/uc-150-start-or-stop-imap-connection.md#mail-already-in-the-inbox), persist each outcome against the source account, mailbox, `UIDVALIDITY`, and message `UID`. A UID identifies a message across sessions while the mailbox's UIDVALIDITY stays the same. If that value changes, the server may reuse UID numbers, so an old outcome cannot be matched by UID alone. [IMAP message identifiers](https://www.rfc-editor.org/rfc/rfc9051.html#section-2.3.1.1)
