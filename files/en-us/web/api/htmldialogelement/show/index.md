---
title: "HTMLDialogElement: show() method"
short-title: show()
slug: Web/API/HTMLDialogElement/show
page-type: web-api-instance-method
browser-compat: api.HTMLDialogElement.show
---

{{ APIRef("HTML DOM") }}

The **`show()`** method of the {{domxref("HTMLDialogElement")}}
interface displays the dialog modelessly, i.e., still allowing interaction with content
outside of the dialog.

## Syntax

```js-nolint
show()
```

### Parameters

None.

### Return value

None ({{jsxref("undefined")}}).

### Exceptions

- `InvalidStateError` {{domxref("DOMException")}}
  - : Thrown if the dialog is already open and modal (i.e., if the dialog has already been opened with {{domxref("HTMLDialogElement.showModal()")}}).

## Examples

The following example shows a simple button that, when clicked, opens a
{{htmlelement("dialog")}} containing a form via the `show()` method. From
there you can click the _Cancel_ button to close the dialog (via the
{{domxref("HTMLDialogElement.close()")}} method), or submit the form via the submit
button.

```html
<!-- Simple pop-up dialog box, containing a form -->
<dialog id="favDialog">
  <form method="dialog">
    <section>
      <p>
        <label for="favAnimal">Favorite animal:</label>
        <select id="favAnimal" name="favAnimal">
          <option></option>
          <option>Brine shrimp</option>
          <option>Red panda</option>
          <option>Spider monkey</option>
        </select>
      </p>
    </section>
    <menu>
      <button id="cancel" type="reset">Cancel</button>
      <button type="submit">Confirm</button>
    </menu>
  </form>
</dialog>

<menu>
  <button id="updateDetails">Update details</button>
</menu>
```

```js
const updateButton = document.getElementById("updateDetails");
const cancelButton = document.getElementById("cancel");
const dialog = document.getElementById("favDialog");
dialog.returnValue = "favAnimal";

function openCheck(dialog) {
  if (dialog.open) {
    console.log("Dialog open");
  } else {
    console.log("Dialog closed");
  }
}

// Update button opens a modeless dialog
updateButton.addEventListener("click", () => {
  dialog.show();
  openCheck(dialog);
});

// Form cancel button closes the dialog box
cancelButton.addEventListener("click", () => {
  dialog.close("animalNotChosen");
  openCheck(dialog);
});
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- The HTML element implementing this interface: {{ HTMLElement("dialog") }}.
