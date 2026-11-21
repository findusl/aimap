# UC 200 — Create a filtering rule

The user wants to tell the service which incoming emails to act on and what to do with them.

## Main flow

1. The user starts a rule for a connected account.
2. The user defines the rule and saves it.
3. The service confirms that the rule was added.

## Business rules

Give the rule a descriptive title, at least one condition, and at least one action. The user chooses the rule's position among the account's rules and whether to stop or continue checking later rules after a match.

### Conditions

| Condition | When it matches |
| --- | --- |
| Text | Choose the sender's display name, sender's email address, or subject. Compare it with text using **contains**, **starts with**, or **ends with**, or check a pattern using **matches a regular expression**. |
| Multiple-choice AI question | The user supplies a question and its answer options, chooses the option to check, and sets a minimum confidence. The model's confidence in that option meets or exceeds the minimum. |
| True-or-false AI question | The model answers the user's question about the email with **true**. |

For either AI condition, the model answers the question directly from the email in a single decision.

The user can reverse any condition with **NOT**. Combine conditions with **all (AND)** or **any (OR)**. Groups can be combined, for example, “the sender's address ends with ‘@supplier.example’ AND (the subject contains ‘invoice’ OR the subject contains ‘receipt’).”

### Actions

- **Move to folder.** Move the email to the chosen folder. As the user types a folder name or path, suggest matching folders from the rule's account and show their full paths.
- **Mark as read.** Mark the matching email as read.

## Alternative flows

### The rule is incomplete or invalid

The service identifies what needs correction, such as an invalid regular expression. The user can correct the rule and save it.
