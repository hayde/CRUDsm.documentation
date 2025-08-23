---
sidebar_position: 2
---

# actionRemovedOrAdded

This action is called, when the list of the elements is changed.

This action is always fired, when the list is initialized (actionInit), a new entry is saved (not actionNew, but actionSave after a actionNew) or an element is deleted (actionDelete).

## Usage

`{statemachine}.actionRemovedOrAdded([optional async] (lastID) => { } );`

In this action, you will typically reload the list elements, visualizing the elements of the state machine for selection or simply to view.

The list element itself is generally not element of the HTML form tag. So the list could be any kind of listed values, like a selection, a combo box, a list of simple links {'<a>'} and so on. The filling or drawing of that elements is up to you.

### Asyncronous
We don't have a sample at the moment, that is asyncronous. Don't hesitate to send us a valid one.

### Syncronous

```js
        crud.actionRemovedOrAdded((lastID) => {
                const keys = crud.getItems();

                const s = document.getElementById("documents");

                // clear all elements first
                while (s.options.length > 0) {
                    s.remove(0);
                }

                // fill afterwards all the new once
                keys.map((key, index) => {
                    var option = document.createElement("option");
                    option.value = key.id;
                    option.text = key.obj;
                    option.selected = index === 0;

                    s.appendChild(option);
                });

            });
```

## Parameter

`lastID` carries the last ID of the changed value. So if new, you have a new ID, if deleted, you will have the deleted ID inside this value. But the value itself (after deletion) is of course no longer in the tuple list.

## Returnvalue

This function does not require a return value.