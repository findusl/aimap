# UC 240 — Reorder filtering rules

The user wants to choose which rules run first for a connected account.

## Main flow

1. The user [views the account's rules](uc-210-view-filtering-rules.md).
2. The user moves a rule to the desired position.
3. The service saves and displays the new order.

## Business rules

Reordering is available when the account has at least two rules. The saved order applies to [sorting incoming email](uc-009-sort-incoming-email.md#business-rules) for that account from the next arrival onward.
