---
sidebar_position: 9
---


# actionDelete

Tha action is fired, when a delete event is fired.  The parameter is the object to be deleted. The return value a true for "yes do it" or false for "no way"

## Usage

`{statemachine}.actionDelete([optional async] ( object) => { return true | false; } );`


### Asyncronous

... i don't hava a good example for that.

### Syncronous

```js
crud.actionDelete( (object) => {
    
    // for example, check if the object is deletable or not
    if( object.name === "root" ) {
        // you can't delete the root
        return false;
    } else {
        return true;
    }
});
```

## Parameter

object - the object, to be delete

## Returnvalue

true or false, if the object deletable or not