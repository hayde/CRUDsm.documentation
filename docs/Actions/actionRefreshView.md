---
sidebar_position: 3
---

# actionRefreshView

Each time, the data is refreshed. Typically after a selection, initially, after a delete (new selection).

Here you simply refesh all elements on the form. like changing content of values of a textbox, change images or dropboxes or checkboxes.

## Usage

`{statemachine}.actionRefreshVew([optional async] (lastID) => { } );`

### Asyncronous
We don't have a sample at the moment, that is asyncronous. Don't hesitate to send us a valid one.

### Syncronous

```js
crud.actionRefreshView( (c) => {
    if (c) {
        crud.activate(["Firstname", "Lastname", "Email", "save", "cancel", "delete"]);
        crud.deactivate(["new"]);

        crud.setField("Firstname", c.Firstname);
        crud.setField("Lastname", c.Lastname);
        crud.setField("Email", c.Email);
    } else {
        crud.deactivate(["Firstname", "Lastname", "Email", "save", "cancel", "delete"]);
        crud.activate["new"];

        crud.setField("Firstname", "");
        crud.setField("Lastname", "");
        crud.setField("Email", "");
    }
});
```

## Parameter

`c` (or current) is the current object, that is validated and ready to be viewed

## Returnvalue

This function does not require a return value.