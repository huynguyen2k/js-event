# Javascript Events

---

### 1. Introduction to events

An event is a signal that something has happened and provides a mechanism by which an action can be automatically taken (that is, some code running) when the event occurs.

For example:

- The user selects, clicks, or hovers the cursor over a button.
- A form is submitted.
- A web page finishes loading.
- A video is played, paused, or ends.

### 2. The overall inheritance for HTML element classes

![MarineGEO circle logo](https://javascript.info/article/basic-dom-node-properties/dom-class-hierarchy.svg)

### 3. Event type

There are many types of events:

| Event type | Description                                                                                                                      | Trigger element                                 |
| ---------- | -------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| Mouse      | Events related to using a computer mouse.                                                                                        | Events fired on: Element                        |
| Keyboard   | Events related to using a keyboard.                                                                                              | Events fired on: Document, Element.             |
| Form       | Events related to forms being constructed, reset and submitted.                                                                  | Events fired on: HTMLFormElement.               |
| Animation  | Events related to the Web Animation API. Used to respond to changes in animation status (e.g. when an animation starts or ends). | Events fired on: Document, Window, HTMLElement. |
| Clipboard  | Events related to the Clipboard API. Used to notify when content is cut, copied, or pasted.                                      | Events fired on: Document, Element, Window.     |
