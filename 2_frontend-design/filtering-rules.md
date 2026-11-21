# Filtering rules

## Rules for one connection

The **Filtering rules** view shows the selected connection's display name, a **Connections** link, and an **Add rule** link. Show **No saved rules** when empty. Otherwise show one `rule-item` per rule in processing order. Each title is a link to a **Rule details** view showing the title, grouped conditions, actions, and stop-or-continue setting. A **Filtering rules** link returns to the list for the same account. [UC 210](../1_features/uc-210-view-filtering-rules.md)

| Within a rule item | Observable result |
| --- | --- |
| **Edit rule** link | Open the editor with this rule's current settings. [UC 220](../1_features/uc-220-edit-filtering-rule.md) |
| **Move up**, **Move down** buttons | Move the rule one position and display the saved order. Disable each direction at its boundary. A test can read the titles in list order after the move and on reopening the list. [UC 240](../1_features/uc-240-reorder-filtering-rules.md) |
| **Delete rule** button | Open a dialog named **Delete rule** showing the rule title. **Cancel** dismisses it. **Delete** confirms, removes the item on success, and shows confirmation. [UC 230](../1_features/uc-230-delete-filtering-rule.md) |

## Rule editor

The heading is **Add rule** or **Edit rule**. Expose a text field labeled **Title**, a numeric **Position** field (1 is first), and a **Continue after match** checkbox. The **Conditions** and **Actions** sections below describe the editable parts of the rule. Their meaning and validity come from [UC 200](../1_features/uc-200-create-filtering-rule.md#business-rules).

### Conditions

Start a new rule with one empty root group. Each group is a `condition-group` containing a **Match** choice of **All (AND)** or **Any (OR)**. Its **Add condition** and **Add group** buttons append a condition or a nested group to that group. A nested group has a **Remove group** button.

Each `condition-item` has a **Condition type** choice, a **Negate** checkbox, and a **Remove condition** button. The selected type exposes these labeled fields.

| Condition type | Controls within the condition |
| --- | --- |
| **Text** | **Field** selects **Sender name**, **Sender address**, or **Subject**. **Comparison** selects **Contains**, **Starts with**, **Ends with**, or **Matches regex**. **Value** holds the text or pattern. |
| **Multiple choice** | Enter the **Question**. **Add option** appends an `answer-option` with an **Answer** field and **Remove option** button. **Option to check** selects among the entered answers. **Minimum confidence (%)** accepts a percentage. |
| **True or false** | Enter the **Question**. |

For nested groups, the nearest enclosing `condition-group` identifies which group owns an **Add condition** or **Add group** button. Rule details preserve the grouping and identify negated conditions so that two expressions with different meanings can be distinguished after saving.

### Actions

**Add action** appends an `action-item` with an **Action type** choice and a **Remove action** button.

| Action type | Controls within the action |
| --- | --- |
| **Move to folder** | **Destination folder** is an editable combobox. Typing opens matching suggestions as options named by their full folder paths. Choosing an option displays that path as the selected value. |
| **Mark as read** | Selecting the type completes the action. |

### Saving

Show validation at the affected field, condition, group, or action. The **Save** button becomes available for a valid rule. On success, return to the account's **Filtering rules** view with confirmation and the rule at its saved position. Opening its details or editor exposes the saved settings.
