---
sidebar_position: 1
---


# Registration

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
    var people_crud = new CRUDsm('people');
</script>
```

As you can see, the registration process itelf is quite simple. When creating the instance, you simply hand over as parameter the name of the form: `var people_crud = new CRUDsm('people');`.

All the necessary lookup, registrations and qulifications of the elements will be done by the statemachine itelf.

__As an example__
the input form will be injected like this: `<input type='text' id='firstname' placeholder='firstname' onchange='people_crud.event_changed();'/>`. That will be valid for all the fields inside the `form` with the id `people`.

Next, lets have a look to all the helpers, CRUDsm is providing you to simplify the usa
The handling itself is splitted into two groups. The Events and the Helpers.
