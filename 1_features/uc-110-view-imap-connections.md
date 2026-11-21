# UC 110 — View saved IMAP connections

The user wants to see which IMAP connections they have saved.

## Main flow

1. The user asks to view their saved connections.
2. The system lists the connections.

From the overview, the user can [start or stop a saved connection (UC 150)](uc-150-start-or-stop-imap-connection.md).

## Business rules

Show the display name, server address, and connection status for each saved connection. If the server lacks new-mail notifications, show **Not connected**, even if the user skipped the connection test.

## Alternative flows

### The user has no saved connections

The system indicates that the user has no saved connections.
