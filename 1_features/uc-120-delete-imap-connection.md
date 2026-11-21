# UC 120 — Delete an IMAP connection

The user wants the service to stop using a saved IMAP connection.

## Main flow

1. The user chooses a saved connection to delete.
2. The system asks the user to confirm the deletion.
3. The user confirms. The system removes the saved connection and reports that it was deleted.

## Business rules

Deletion applies only to the connection saved in the service. The service stops using the deleted connection to access the mailbox.

## Alternative flows

### The user cancels

The system ends the deletion flow.
