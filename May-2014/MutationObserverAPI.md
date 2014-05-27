#Mutation Observer

> MutationObserver provides developers a way to react to changes in a DOM. It is designed as a replacement for Mutation Events defined in the DOM3 Events specification.


There are three main type of observations defined currently, `attribute`, `childList` and `characterData`, which I'll go through briefly below. Please note, however, that this is a newer API and *may not be available* in some browsers (although there are polyfills and `Mutation Events` to fall back upon).

### `attribute`

> mutations to target's children are to be observed.

This setting watches for a change to a DOM nodes attribute within the target node. Examples of this type of mutation would be adding/remvoing/replacing DOM nodes. There are two options that go along with this: `attributeOldValue` and `attributeFilter` that are described below.

### `childList`

> mutations to target's attributes are to be observed.

The observer will let you know when an attribute changes within the context it's observing. An example of this type of mutation would be adding a `class` to a given node. There are two helpful options that accompy this type of mutation, `attributeOldValue` and `attributeFilter`, which are covered below.

### `characterData`

> mutations to target's data are to be observed.

*CharacterData is an abstract interface and does not exist as node. It is used by Text, Comment, and ProcessingInstruction nodes*

### Other Options

##### `subtree`

> target's descendants are to be observed.

##### `characterDataOldValue`

> target's data before the mutation needs to be recorded.

##### `attributeOldValue`

> target's attribute value before the mutation needs to be recorded.

Passes along the previous value of the attribute that was changed within the `mutation` object in the callback function.

##### `attributeFilter`

> Set to an array of attribute local names (without namespace) if not all attribute mutations need to be observed.



### Example
```javascript
    
    //target to listen for observations within
    var target = document.querySelector("html");
    
    // create an observer instance
    var observer = new MutationObserver(function(mutations) {
      mutations.forEach(function(mutation) {
          console.log(mutation);
      });
    });

    // configuration of the observer:
    var config = {
        attributes: true,
        childList: true,
        characterData: true,
        subtree: true,
        attributeOldValue: true,
        characterDataOldValue: true
    };

    // pass in the target node, as well as the observer options
    observer.observe(target, config);
```


###Polyfill

https://github.com/Polymer/MutationObservers
