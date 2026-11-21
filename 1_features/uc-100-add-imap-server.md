# UC 100 — Add an IMAP server

The user wants to connect an existing IMAP mailbox so the service can sort its messages.

## Main flow

1. The user provides the input for a new IMAP server.
2. The system automatically validates the input as it changes.
3. The user saves the configuration, and the system confirms that the server was added.
4. The system automatically [starts the saved connection (UC 150)](uc-150-start-or-stop-imap-connection.md#business-rules).

## Business rules

| Setting | Requirement |
| --- | --- |
| Display name | Supply a non-blank name to identify the connection in the service. |
| Server address | Supply the hostname or IP address of the IMAP server. |
| Port | Use a port from 1 to 65535. Default to 993 for implicit TLS and 143 for STARTTLS or an unencrypted connection. The user can supply a different port. |
| Connection security | Choose implicit TLS, STARTTLS, or an unencrypted connection. Default to implicit TLS. |
| Authentication | Choose whether to log in. If login is selected, supply a username and password. |

The user can save valid input before or after testing, regardless of the test result.

## Alternative flows

### Input validation fails

The system identifies what needs correction. The user can correct the input and retry.

### Test the connection

The user can [test the connection before saving (UC 140)](uc-140-test-imap-connection.md).
