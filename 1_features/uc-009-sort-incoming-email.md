# UC 009 — Sort incoming email

The user wants new mail handled according to their rules even when their mail client is closed.

## Main flow

1. The service loads an email from the connected account's inbox.
2. The service checks the account's rules and determines which actions apply.
3. The service applies those actions to the email on the mail server, so the user sees the result in their mail clients.

## Business rules

Check rules in the account's configured order. Skip a rule whose conditions do not match. On a match, include its actions and follow its stop-or-continue setting. The [rule definition](uc-200-create-filtering-rule.md#business-rules) specifies how conditions match and what each action does.

Apply the collected actions in rule order. If several matching rules move the email, the last move reached determines its final folder. A move made while sorting counts as part of the original arrival.

The service remembers an email as processed once all applicable actions succeed or it determines that no rule matches.

The service records sorting errors in its logs for monitoring.

## Timing

Sorting starts immediately when a new email arrives in the inbox.

## Alternative flows

### No rule matches

The service finishes processing the email without taking any action.

### The AI cannot answer a required question

The service records an error, skips all actions for that email, and continues with other arrivals.

### An action fails

The service records the action error, marks the email as failed, and skips its remaining actions. It continues sorting other emails.

### The email was deleted during sorting

The service stops processing that email and continues with other arrivals.
