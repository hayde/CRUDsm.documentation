---
sidebar_position: 6
---


# actionChanged

Whenever data has been changed in the entry forms, this action will be fired. It will give the GUI the possiblity to mark the status of a changed document, or to activate buttons ( like save, cancel, ... ) or any other elements about that occurence.

## Usage

`{statemachine}.actionChanged([optional async] (current) => {} );`

### Asyncronous
We don't have a sample at the moment, that is asyncronous. Don't hesitate to send us a valid one.

### Syncronous

```js
crud.actionChanged( () => {
    // the crud.activate'er function will enable the html elements for the form elements "save" and "cancel".
    crud.activate( ["save", "cancel"]);
});
```

## Parameter

none

## Returnvalue

none