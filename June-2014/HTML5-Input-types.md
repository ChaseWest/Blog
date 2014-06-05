#HTML5 Input Types

  All types are viewable [here](http://jsfiddle.net/ChaseWest/4pFmg/);

  HTML5 introduces many new additions, a small fraction of which are new `input` types. First, lets review the current types provided prior:

###Old Types
------

#####text

> One-line plain-text edit control for the input element’s value.

#####password

> One-line plain-text edit control for entering a password.

#####checkbox

> Represents a state or option that can be toggled.

#####radio

> Represents a selection of one item from a list of items. 

#####button

> Button with no additional semantics.

#####submit

> Button for submitting a form. 

#####reset

> Button for resetting a form.

#####file

> Represents a list of file items.

#####hidden

> Represents a value that is not intended to be examined or manipulated by the user.

#####image

> Either an image from which the UA enables a user to interactively select a pair of coordinates and submit the form, or alternatively a button from which the user can submit the form.


###New Types
------

*Note: If the browser does not support the given type it will revert to using a type of `text`*

#####datetime
#####datetime-local
#####date
#####month
#####time
#####week
#####number
#####range
#####email
#####url
#####search
#####tel
#####color


###Examples
------

```html
<input type="text"></input>
<input type="password"></input>
<input type="checkbox"></input>
<input type="radio"></input>
<input type="button"></input>
<input type="submit"></input>
<input type="reset"></input>
<input type="file"></input>
<input type="hidden"></input>
<input type="image"></input>
<input type="datetime"></input>
<input type="datetime-local"></input>
<input type="date"></input>
<input type="month"></input>
<input type="time"></input>
<input type="week"></input>
<input type="number"></input>
<input type="range"></input>
<input type="email"></input>
<input type="url"></input>
<input type="search"></input>
<input type="tel"></input>
<input type="color"></input>
```
