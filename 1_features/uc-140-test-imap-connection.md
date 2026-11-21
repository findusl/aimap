# UC 140 — Test an IMAP connection

The user wants to know whether their current connection settings support automatic sorting.

## Main flow

1. The user selects **Test connection**.
2. The service tests the current settings, including any unsaved changes, and reports success.

## Business rules

The test passes when the service can access the mailbox using those settings and the server supports new-mail notifications.

## Alternative flows

### The test fails

The service reports the failure and gives the reason when known. If the server lacks new-mail notifications, it reports “This server cannot notify the service when new mail arrives, so automatic sorting is unavailable.”

The user can adjust the settings and run the test again.
