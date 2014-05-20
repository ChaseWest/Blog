#Mutation Observer

> MutationObserver provides developers a way to react to changes in a DOM. It is designed as a replacement for Mutation Events defined in the DOM3 Events specification.


There are three main type of observations defined currently, `attribute`, `childList` and `characterData`, which I'll go through briefly below. Please note, however, that this is a newer API and *may not be available* in some browsers (although there are polyfills and `Mutation Events` to fall back upon).

### `attribute`

> mutations to target's children are to be observed.

### `childList`

> mutations to target's attributes are to be observed.

### `characterData`

> mutations to target's data are to be observed.

### Other Options

##### `subtree`

> target's descendants are to be observed.

##### `characterDataOldValue`

> target's data before the mutation needs to be recorded.

##### `attributeOldValue`

> target's attribute value before the mutation needs to be recorded.

##### `attributeFilter`

> Set to an array of attribute local names (without namespace) if not all attribute mutations need to be observed.

### Example
```javascript
    // create an observer instance
    var observer = new MutationObserver(function(mutations) {
      mutations.forEach(function(mutation) {
          _log(mutation);
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
