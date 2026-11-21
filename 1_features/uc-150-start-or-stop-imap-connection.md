# UC 150 — Start or stop an IMAP connection

The user wants to control when the service watches a saved account for incoming mail.

## Main flow

1. From the connection overview, the user chooses **Start** or **Stop** for a saved connection.
2. The service carries out the request and shows the resulting connection status.

## Business rules

- **Start** uses the saved settings to connect to the mailbox. Once the service is listening for new mail, it shows **Connected** and [sorts incoming email](uc-009-sort-incoming-email.md).
- **Stop** disconnects the service from the mailbox and shows **Not connected**. Sorting is paused for that account until the user starts it again. The saved settings and rules are available for the next start.

### Mail already in the inbox

On the first start, the service sorts every email already in the inbox. When it resumes after a deliberate stop or a service interruption, it sorts all inbox emails except those already recorded as processed or failed.

## Alternative flows

### The connection cannot start

If the saved settings or server fail to meet the [connection requirements](uc-140-test-imap-connection.md#business-rules), the service shows **Not connected** and explains the failure when the reason is known. The user can retry.
