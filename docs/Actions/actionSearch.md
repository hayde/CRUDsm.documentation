---
sidebar_position: 11
---


# actionSearch

This action is fired after the init search is fired, and the form is rearranged for a search form.

After the rearrangement, the user fill out everything necessary for the search and clicked "search" finally.

## Usage

`{statemachine}.actionSearch([optional async] () => { return list; } );`

__Important:__
In search, you have to read all the values from the fields

### Asyncronous
```js
crud.actionSearch( async () => {

    const search_name = crud.getField( "lastname" );

    const search_results = await deepjson.get( "tr.nested.customers.addresses", null, `result = data.filter( (x) => { return x.firstname == '${search_name}';`)0;
    
    return search_results;
});
```

### Syncronous

```js
crud.actionSearch( async () => {

    const search_name = crud.getField( "lastname" );

    const search_results = cache.get( "customer_addresses" ).filter( (x) => { return x.firstname == search_name; } );
    
    return search_results;
});
```

## Parameter

none

## Returnvalue

A list of elements matching the search algorithm.