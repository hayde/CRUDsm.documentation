---
sidebar_position: 4
---


# actionNew

The action new is fired, when the user initiated a new creation of a new item for the entire list.

This action takes no parameter, but need to create a new object for the list and returns this value.

## Usage

`{statemachine}.actionNew([optional async] () => { return new_object; } );`

### Asyncronous
We don't have a sample at the moment, that is asyncronous. Don't hesitate to send us a valid one.

### Syncronous

```js
crud.actionNew( () => {
    var c = new Contact();
    return c;
});
```

## Parameter

none

## Returnvalue

The new Element, which has to be stored in the array list