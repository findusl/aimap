# UC 130 — Edit an IMAP connection

The user wants to change the settings of a saved IMAP connection.

## Main flow

1. The user chooses a saved connection to edit.
2. The system presents its current settings for editing.
3. The user changes the settings, and the system [validates the input as in UC 100](uc-100-add-imap-server.md#main-flow).
4. The user saves. The system updates the existing connection and confirms the change.

## Business rules

Apply the [business rules in UC 100](uc-100-add-imap-server.md#business-rules) to the settings being edited.

The system indicates when a password is stored. The user can keep the stored password or enter a replacement.

## Alternative flows

### Input validation fails

Follow [the validation failure flow in UC 100](uc-100-add-imap-server.md#input-validation-fails).

### Test the connection

The user can [test the connection before saving (UC 140)](uc-140-test-imap-connection.md).
