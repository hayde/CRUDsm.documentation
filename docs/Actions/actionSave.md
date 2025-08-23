---
sidebar_position: 7
---


# actionSave

The action new is fired, when the user initiated a new creation of a new item for the entire list.

This action takes no parameter, but need to create a new object for the list and returns this value.

## Usage

`{statemachine}.actionSave([optional async] ( object, Id) => { return object_to_save; } );`

__Important:__
If the `Id` is empty, then the object is a new object. Otherwise it is an existing object already and will be overwritten.


### Asyncronous
```js
crud.actionNew( async ( object, id) => {

    // function code to load
    var value;
    
    if( id ) {
        // value was existing already, so replace the existing
        value = await deepjson.put( "tr.nested.customers.addresses", object );
    } else {
        // value was not existing, so add a new entry to the database

        // get new id
        object.id = await deepjson.put( "tr.nested.customers.addresses", null, "result = data.length;");

        
        value = await deepjson.post( "tr.nested.customers.addresses", object );
    }
    return values;

});
```

### Syncronous

```js
crud.actionNew( (object, id) => {
    
    if( ! id ) {
        object.id = cache.get( "customer_addresses" ).length; 
    }

    const value = cache.set( "customer_addresses", object );
    return value;
});
```

## Parameter

object - the object, to be stored
id - the ID of the object to be stored. if id is empty, then it is a newly generated object.

## Returnvalue

The new Element, which has to be stored in the database / storage