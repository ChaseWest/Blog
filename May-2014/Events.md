# [Events](https://developer.mozilla.org/en-US/docs/Web/API/Event)

## Event Binding

### Basics

Events are generally fairly simple - you have a `DOM` element that you want to perform a given function:

```javascript
  var button = document.querySelector("button");
  
  button.onclick = function(){
    alert("click");
  }
```

In this [example](http://jsfiddle.net/ChaseWest/S5Req/1/), the `button` element `fires` an `onclick` event whenever it is clicked. 

Consider though, what happens when you want to `bind` an `event` to multiple `DOM` nodes to fire the same event? 

```html
  <ul>
      <li>item 1</li>
      <li>item 2</li>
      <li>item 3</li>
      <li>item 4</li>
  </ul> 
```

```javascript
  var items = document.querySelectorAll("li");
  
  for(var i = 0; i < items.length; i++){
      items[i].onclick = function(){
          alert("Hi from " +  this.innerText);    
      }
  }
```

For something as simple as the above [example](http://jsfiddle.net/ChaseWest/5hYcU/), you would need to `loop` through each list `element` and bind the same `event` to each `li`. You can see how this would quickly get out of control and difficult to maintain. 

How would you `bind` an `event` to an `element` that was dynamically created by your Javascript code (ex: new rows in a table)? What about an `element` that's removed from the `DOM`? If you're unsure, by all means, give it a try. You'll find that it becomes quite difficult and tedious to keep track of. 

Lucky for you (and the rest of us), we have **Event Delegation**!

### Event Delegation

The overall idea here is simple: We `bind` our `event` to a `parent` node that listens for any type of `event` that happens within it. Knowing this, lets update the above [example](http://jsfiddle.net/ChaseWest/5hYcU/2/):

```javascript
var items = document.querySelector("ul");
  
items.onclick = function(){
    alert("Hi from " +  this.innerText);    
}
```

You'll notice a few things here:

  - We've changed from `querySelectorAll` to `querySelector`. Since we're only wanting one `parent` node to `bind` our event to, it makes more sense to use `querySelector`.
  - We only have one `element` now, so there's no need for the `for` loop.
  - Finally, if you run this example you should notice one final detail. `this.innerText` is returning all the list items any time you click **ANY** of them. This is because the `this` inside the `event` is now the `ul` node that we bound the event to. 

We can, however, get the node that was clicked by using the `event` *object* that gets passed to our `function`.

##### The `event` object

>  Warning - I'm not going into the full details here, but in older versions of IE you'll need to check `window.event`. Something like this: `var e = e || window.event` should do the trick.

```javascript
var items = document.querySelector("ul");
  
items.onclick = function(e){
    alert("Hi from " +  e.target.innerText);    
}
```

You'll notice the following changes:

- In this [example](http://jsfiddle.net/ChaseWest/5hYcU/3/) we've included an `e` argument that gets passed to all `event` callback functions. 
- We've also changed `this` inside our function to `e.target` which is the `element` within the `parent` that caused the `event`.  

#### attachEvent vs addEventListener

##### [addEventListener](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget.addEventListener)

>   target.addEventListener(event, listener[, useCapture]);

- **target** - The DOM node that you want to bind the `event` to. 
- **event** - The string representation of the event, ex: "click", "change", etc..
- **listener** - 
- **useCapture (optional)**

##### [attachEvent](http://msdn.microsoft.com/en-us/library/ie/ms536343(v=vs.85).aspx)

>   target.attachEvent(event, listener)

Now that we know a bit more about what we need to do, lets dive into what makes this possible.

### Event Propagation

There are two forms of Event Propagtion (Event Bubbling and Event Capturing), however only **Event Bubbling** is supported by all major browsers. 

##### [Event Bubbling](http://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-flow-bubbling)

>   The process by which an event propagates upward through its ancestors after being handled by the event's target.

Here events are fired on the `element` that received the action (click, change, etc..) and bubble up to the parent nodes, firing any events bound to those elements as well. 

##### [Event Capturing](http://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-flow-capture)

>   The process by which an event can be handled by one of the event's target's ancestors before being handled by the event's target.

Using event capturing, you get the reverse of event bubbling, in that the parent node may fire the event first.


There's a great article [here](http://www.quirksmode.org/js/events_order.html) on event propagation.

### Performance  

As you can probably tell by now, Event Delegation can dramatically increase the performance of your site. But better than that, it's also much easier to manage. You don't need to worry about adding or removing handlers when dynamic elemnts are added to/removed from the DOM.  
