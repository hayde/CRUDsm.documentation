---
sidebar_position: 3
---


# Helpers

CRUDsm will handle the elements inside a form for you.

To link a CRUDsm with a HTML form, you have to register that form with the statemachine.

__Important rules:__

* the list selection need to be outside the `form` html tag
* the attribute `name` is irrelevant to CRUDsm, but `id` is crucial
* you must fire the events like `save`, `delete`, `search` and `cancel` inside your code 
* to fire the events in your html attributes, the CRUDsm instance, has to be global.

__Example:__
```html

<!-- selection list for the names of the people: OUTSIDE THE FORM -->
 <div class="column" id="listselection">
    <select id="peoples" size="30">

    </select>
</div>

<!-- form elements to edit the names  -->
<form name='people'>
    <label for='firstname'>firstname</label>
    <input type='text' id='firstname' placeholder='firstname'/>
    <label for='lastname'>lastname</label>
    <input type='text' id='lastname' placeholder='lastname'/>
    <button type='delete' id='delete' onclick='people_crud.event_delete()'>delete</button>
    <button type='button' id='cancle' onclick='people_crud.event_cancel()'>cancel</button>
    <button type='button' id='save' onclick='people_crud.event_save()'>save</button>
</form>

<script>
    // initialize the form with then name 'people'.
    // the instance of crudms need to be public 
    var people_crud = new CRUDsm('people')
</script>
```

As you can see, the registration process itelf is quite simple. When creating the instance, you simply hand over as parameter the name of the form.

All the necessary lookup, registrations and qulifications of the elements will be done by the statemachine itelf.

Next, lets have a look to all the helpers, CRUDsm is providing you to simplify the usa
The handling itself is splitted into two groups. The Events and the Helpers.

## Register

## Events

Events are fired accoding to the behaviour of the user. A user could enter an value inside a textbox ('input type=text'), change a drop down box ('select'), click a checkbox ('input type=checkbox'), change a radio selection ('input type=radio') or enter values into a multiple line textbox (textarea).

The user could although click the save button, a delete button, a cancel buttor or the search button.




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