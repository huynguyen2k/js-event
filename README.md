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

### 4. Event handlers

#### HTML-attribute

A handler can be set in HTML with an attribute named on\<event>.
For instance, to assign a click handler for an input, we can use onclick, like here:

```html
<input value="Click me" onclick="alert('Click!')" type="button" />
```

#### DOM property

We can assign a handler using a DOM property on\<event>.
For instance, elem.onclick:

```html
<input id="elem" type="button" value="Click me" />
<script>
  const elem = document.getElementById('elem')
  elem.onclick = function () {
    alert('Thank you')
  }
</script>
```

To remove a handler – assign elem.onclick = null.

#### addEventListener

The fundamental problem of the aforementioned ways to assign handlers is that we can't assign multiple handlers to one event.

Let's say, one part of our code wants to highlight a button on click, and another one wants to show a message on the same click.

We'd like to assign two event handlers for that. But a new DOM property will overwrite the existing one:

```js
input.onclick = function () {
  alert(1)
}
// ...
input.onclick = function () {
  alert(2)
}
```

Developers of web standards understood that long ago and suggested an alternative way of managing handlers using the special methods addEventListener and removeEventListener which aren't bound by such constraint.

The syntax to add a handler:

```js
element.addEventListener(event, handler, [options])
```

To remove the handler, use removeEventListener:

```js
element.removeEventListener(event, handler, [options])
```

Multiple calls to addEventListener allow it to add multiple handlers, like this:

```html
<input id="elem" type="button" value="Click me" />

<script>
  function handler1() {
    alert('Thanks!')
  }

  function handler2() {
    alert('Thanks again!')
  }

  const elem = document.getElementById('elem')
  elem.addEventListener('click', handler1) // Thanks!
  elem.addEventListener('click', handler2) // Thanks again!
</script>
```

### 5. Bubbling and capturing

![Bubbling and capturing](https://javascript.info/article/bubbling-and-capturing/eventflow.svg)
