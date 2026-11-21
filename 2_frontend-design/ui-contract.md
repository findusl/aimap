# Browser UI contract

Opening the application shows [Connections](connections.md). Each saved connection leads to its [Filtering rules](filtering-rules.md). The screen contracts specify what a user can find, do, and observe. Their linked use cases define which business outcomes are correct.

## Finding controls

- A screen has a main landmark and the heading given in its contract. Links open views. Buttons perform the named actions. Form fields have associated, visible labels. Names in bold are the English labels that a browser test can rely on.
- Locate a button or link by its accessible role and name, and an input by its label. Each contracted control is identifiable within its screen, dialog, or item. CSS classes, element nesting, and component names are implementation details.
- Repeated items expose the documented `data-testid` on their container. A test can find a connection by its displayed name and server address, then look **within that item** for a button such as **Start**. Use fixture data with recognizable names.
- Each repeated item also exposes a `data-ui-key` unique for its item type within the view. Keys stay with items through edits and reordering. Saved connection and rule keys also survive navigation and reload. A test can read a key from the rendered item and reuse it after a rename. The value is opaque to the test.

For example, to observe a manual start, find the `connection-item` displaying the fixture connection, activate its **Start** button, then wait for **Connected** within that same item. This uses only the browser-visible interface.

## Observing outcomes

- Controls support keyboard operation. Expose selection, checked, expanded, invalid, and disabled states through the control's standard browser semantics as applicable.
- Show field validation next to the relevant control and associate the message with it. A disabled **Save** and the identified invalid fields make a blocked save observable.
- Announce progress and success as visible status messages and failures as visible alerts in the affected view. On completion, replace pending feedback with the result. Tests wait for that result. Exact feedback wording is fixed only where a screen contract or use case supplies it.
- A saved change is visible when the user revisits the view or reloads the app and opens it again. A confirmation dialog identifies its target, offers the contracted buttons, and returns focus to an available control when dismissed.

For automatic sorting, the browser exposes the saved rule and the connection status. The observable result of a move or a mark-as-read action is the message's folder or read state in the test mailbox. [UC 009 — Sort incoming email](../1_features/uc-009-sort-incoming-email.md#main-flow)

The contracts can be exercised with any browser automation tool that reads roles, labels, visible text, and public attributes. [W3C guidance on accessible names](https://www.w3.org/WAI/ARIA/apg/practices/names-and-descriptions/) · [Examples of browser locators](https://playwright.dev/docs/locators)
