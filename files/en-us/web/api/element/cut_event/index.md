---
title: "Element: cut event"
short-title: cut
slug: Web/API/Element/cut_event
page-type: web-api-event
browser-compat: api.Element.cut_event
---

{{APIRef}}

The **`cut`** event of the [Clipboard API](/en-US/docs/Web/API/Clipboard_API) is fired when the user has initiated a "cut" action through the browser's user interface.

If the user attempts a cut action on uneditable content, the `cut` event still fires but the event object contains no data.

The event's default action is to copy the current selection (if any) to the system clipboard and remove it from the document.

A handler for this event can _modify_ the clipboard contents by calling {{domxref("DataTransfer.setData", "setData(format, data)")}} on the event's {{domxref("ClipboardEvent.clipboardData")}} property, and cancelling the default action using {{domxref("Event/preventDefault", "event.preventDefault()")}}.

Note though that cancelling the default action will also prevent the document from being updated. So an event handler which wants to emulate the default action for "cut" while modifying the clipboard must also manually remove the selection from the document.

The handler cannot _read_ the clipboard data.

It's possible to construct and dispatch a [synthetic](/en-US/docs/Web/API/Document_Object_Model/Events#creating_and_dispatching_events) `cut` event, but this will not affect the system clipboard or the document's contents.

This event [bubbles](/en-US/docs/Learn_web_development/Core/Scripting/Event_bubbling) up the DOM tree, eventually to {{domxref("Document")}} and {{domxref("Window")}}, is [cancelable](/en-US/docs/Web/API/Event/cancelable) and is [composed](/en-US/docs/Web/API/Event/composed).

## Syntax

Use the event name in methods like {{domxref("EventTarget.addEventListener", "addEventListener()")}}, or set an event handler property.

```js-nolint
addEventListener("cut", (event) => { })

oncut = (event) => { }
```

## Event type

A {{domxref("ClipboardEvent")}}. Inherits from {{domxref("Event")}}.

{{InheritanceDiagram("ClipboardEvent")}}

## Examples

### Live example

#### HTML

```html
<div class="source" contenteditable="true">Cut text from this box.</div>
<div class="target" contenteditable="true">And paste it into this one.</div>
```

```css hidden
div.source,
div.target {
  border: 1px solid gray;
  margin: 0.5rem;
  padding: 0.5rem;
  height: 1rem;
  background-color: #e9eef1;
}
```

#### JavaScript

```js
const source = document.querySelector("div.source");

source.addEventListener("cut", (event) => {
  const selection = document.getSelection();
  event.clipboardData.setData("text/plain", selection.toString().toUpperCase());
  selection.deleteFromDocument();
  event.preventDefault();
});
```

#### Result

{{ EmbedLiveSample('Live_example', '100%', '120px') }}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("Element/copy_event", "copy")}} event
- {{domxref("Element/paste_event", "paste")}} event
