#Document Fragments

##[The DOM](https://developer.mozilla.org/en-US/docs/DOM)

> The Document Object Model (DOM) is an API for manipulating HTML and XML documents. It provides a structural representation of the document, enabling you to modify its content and visual presentation by using a scripting language such as JavaScript.

The DOM API allows us, as developers, to modify the content of a given page. From adding
table rows to changing classes to removing list nodes, you've no doubt spent plenty of time
manipulating the DOM to enhance the user experience - and that's a ~~good~~ **GREAT** thing.

Lets see an example of a situation where you would a basic DOM API function:

```html
<ul id="list"></ul>
<button id="button">Add List Item</button>
```

```javascript
var list = document.querySelector("#list");
var button = document.querySelector("#button");

button.onclick = addListItem;

function addListItem(){
  list.innerHTML += "<li>Added</li>";
};
```

In the above [example](http://jsfiddle.net/ChaseWest/JU2vp/) we're using one of the basic functions of
the DOM API, `querySelector`. What this (`document.querySelector("#list")`) says is that within a given
container, `document`, find an `element` that matches the given CSS selector. If you're familiar with
CSS Selectors (or jQuery) this should look familiar. If not you can read more about them [here](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_Started/Selectors).

That seems simple enough, right?

It's not always best to modify the `innerHTML`, so lets use a few other DOM API methods to create our
list element.

```javascript
...

function addListItem(){
  var listItem = document.createElement("li");
      listItemText = document.createTextNode("Added");

  listItem.appendChild(listItemText);
  list.appendChild(listItem);
};

```

In our modified [example](http://jsfiddle.net/ChaseWest/JU2vp/1/) we use the DOM API to create an `li` element
and the text content to go within it. You'll notice this is a bit more work than just using `innerHTML`, but
there are a few security benefits associated with using this method. I won't go into all the details here, as it
could easily be a topic of its own. Feel free to look more into it, however, because many others have went more
in depth regarding its issues.

What if we wanted to add many elements at once? For example, what if our above function adds 10 new list items
each time we click the button.


```javascript
...

function addListItem(){
  var listItemText,
      listItem;

  for(var i = 0; i < 10; i++){
    listItemText = document.createTextNode("Added")  
    listItem = document.createElement("li");
    listItem.appendChild(listItemText);
    list.appendChild(listItem);
  }

};

```

[Here](http://jsfiddle.net/ChaseWest/JU2vp/3/) we can see that we're adding the new list elements to the DOM on
each iteration of our loop. While at first this may not seem like an issue, if you're modifying many aspects of
the DOM in you Javascript code, it can have a significant impact on your performance.


##[Reflow](http://www-archive.mozilla.org/newlayout/doc/reflow.html)

> Reflow is the process by which the geometry of the layout engine's formatting objects are computed.

When you change an aspect of the DOM, the browser must adjust any geometry that
may have changed. It's simple to see here that by adding elements over and over
to the DOM that the geometry on the page must be recalculated each time. Going
back to our example above, the page would be forced to reflow each time we add
a new `li` to the DOM.

##Document Fragments

Document Fragments give us the ability to create an empty document object
that we can append our elements to. Rewriting our above example one last time
(I promise), we can take advantage of this:

```javascript
...

function addListItem(){
  var fragment = document.createDocumentFragment(),
      listItemText,
      listItem;

  for(var i = 0; i < 10; i++){
    listItemText = document.createTextNode("Added")  
    listItem = document.createElement("li");
    listItem.appendChild(listItemText);
    fragment.appendChild(listItem);
  }

  list.appendChild(fragment);

};

```
Just a few changes here:

- We created a document fragment using `document.createDocumentFragment()`
- Then we append each `listItem` to the `fragment`
- Once all the listItems are created, we append our fragment to the `list`

##Conclusion

Why even care? It seems like more work that you shouldn't have to care about, right?
I would disagree - I'm only scratching the surface with my above examples.
There are may benefits to reducing the amount of reflows and increasing the
performance of your DOM interactions. The less you touch the DOM, the better.
