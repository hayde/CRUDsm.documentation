---
sidebar_position: 10
---


# actionInitSave

Typically, this action is called after the user of a GUI clicks the "search" button on a form. Then you have to arrange the form accordingly.

It might be, that you:

1. open a single textbox to search for free text
1. clear all fields and let the user fill out that fields for search entries
1. open a text above the list element to search for a key only

Or what ever comes into your mind.

## Usage

`{statemachine}.actionInitSearch([optional async] () => {} );`


### Asyncronous

I have here no good example to view.

### Syncronous

```js
crud.actionInitSearch( () => {
    
    // I will be happy to have a good example here :)
});
```

## Parameter

none

## Returnvalue

none