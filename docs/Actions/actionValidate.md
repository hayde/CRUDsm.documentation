---
sidebar_position: 5
---


# actionValidate

When the user changed data from an element of the array list, then this object need to be validated, if all the data is valid or not.

This function need to cover the consistency of the input data. If everything is ok, the returnvalue is true, otherwise false.

## Usage

`{statemachine}.actionValidate([optional async] (current) => { return [true|false]; } );`

### Asyncronous
We don't have a sample at the moment, that is asyncronous. Don't hesitate to send us a valid one.

### Syncronous

```js
crud.validate( (c) => {
    
});
```

## Parameter

none

## Returnvalue

The new Element, which has to be stored in the array list.

Or:
If no element was created, then `undefined` to abort the creation of a new object