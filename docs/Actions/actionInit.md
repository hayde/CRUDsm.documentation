---
sidebar_position: 1
---

# actionInit

The init function initializes all data to the StateMachine.

If you have a database connection, here you should get all elements, you want to have in your state machine handled, loaded.

## Usage

`{statemachine}.actionInit([optional async] () => { return value_array; });`

### For asynchronous calls

It is quite common, that you retrieve the values from a database, so you - mostly - have to add the `async () =>` specifier before the function. Then inside the loading routine, I suggest, that you work with await to retrieve the value. That will make you code easier to read.

```js

const crud = new CRUDsm();

crud.actionInit( async () => { 
    // function code to load
    const values = await deepjson.get( "tr.nested.customers.addresses" );
    return values;
})

```

### for synchronous calls

But if you have the values already in a kind of cache, then you simply load the values in a syncronous call and avoid the async declaration.

```js

const crud = new CRUDsm();

crud.actionInit( () => { 
    // function code to load
    const values = cache.get( "customer_addresses" );
    return values;
})

```

## Parameter

No parameter will be given.

## ReturnValue

## Samples