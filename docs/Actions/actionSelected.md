---
sidebar_position: 8
---


# actionSelected

if you have a list of elements, you are able to select one of them. This action occures, if the selection is done.

This mainly important to rearrange elements on the screen, or load nested crud objects according to the new selection.

## Usage

`{statemachine}.actionSelected([optional async] ( Id ) => { return false | id; } );`

__Important:__
If the `Id` is empty, then the object is a new object. Otherwise it is an existing object already and will be overwritten.


### Asyncronous
```js
crud.actionSelected( async ( id ) => {

    // inform the other clients, that there is a selection change
    client.send( 'skip', id );

    return true;

});
```

### Syncronous

```js
crud.actionNew( (id) => {
    
    // inform the other clients, that there is a selection change
    client.send( 'skip', id );

    // return the selected id back, or anotherone.
    return id;
});
```

## Parameter

id of the new selected object

## Returnvalue

If false, then the selection will be interrupted
If true, the selection is confirmed. A possible autosave will be fired