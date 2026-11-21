# Connections

## Overview

The entry view has the heading **Connections** and an **Add connection** link. When the list is empty, show **No saved connections** and keep the add link available. Each saved entry is a `connection-item` as defined in the [UI contract](ui-contract.md#finding-controls).

| Within a connection item | Observable result |
| --- | --- |
| Display name, server address, and connection status | The status is visible as text. Its value follows [UC 110](../1_features/uc-110-view-imap-connections.md). |
| **Start** or **Stop** button | Offer **Start** when disconnected and **Stop** when connected. Show the resulting status on the item and any failure reason there. [UC 150](../1_features/uc-150-start-or-stop-imap-connection.md) |
| **Edit connection** link | Open the editor populated with this connection's settings. [UC 130](../1_features/uc-130-edit-imap-connection.md) |
| **Filtering rules** link | Open this account's [rules view](filtering-rules.md). |
| **Delete connection** button | Open a dialog named **Delete connection** showing the display name and server address. **Cancel** dismisses it. **Delete** confirms, removes the item on success, and shows confirmation. [UC 120](../1_features/uc-120-delete-imap-connection.md) |

## Connection editor

The heading is **Add connection** or **Edit connection**. Use the input requirements and defaults from [UC 100](../1_features/uc-100-add-imap-server.md#business-rules). These labels identify the editor controls.

| Label | Control |
| --- | --- |
| **Display name**, **Server address** | Text inputs |
| **Port** | Numeric input |
| **Connection security** | Single choice among **Implicit TLS**, **STARTTLS**, and **Unencrypted** |
| **Use login** | Checkbox. When checked, show **Username** and **Password** inputs. |
| **Password** | Masked input. When editing a saved password, show **Password saved** and leave the replacement input empty. |

**Test connection** and **Save** are separate buttons. Show the test result inside the editor, using the failure message from [UC 140](../1_features/uc-140-test-imap-connection.md#the-test-fails) when applicable. After a test failure the entered values are still available, and valid input can be saved. Field validation updates as the user edits.

On successful save, return to **Connections**, show confirmation, and display the saved item. For a new connection, its status reflects the automatic start specified in [UC 100](../1_features/uc-100-add-imap-server.md#main-flow). A failed start is visible on the saved item.
