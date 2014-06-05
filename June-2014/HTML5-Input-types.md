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

> Control for setting the element’s value to a string representing a global date and time.

#####datetime-local

> Control for setting the element’s value to a string representing a local date and time.

#####date

> Control for setting the element’s value to a string representing a date.

#####month

> Control for setting the element’s value to a string representing a month.

#####time

> Control for setting the element’s value to a string representing a time.

#####week

> Control for setting the element’s value to a string representing a week.

#####number

> Precise control for setting the element’s value to a string representing a number.

#####range

> Imprecise control for setting the element’s value to a string representing a number.

#####email

> Control for editing an e-mail address or list of e-mail addresses given in the element’s value.

#####url

> Control for editing an absolute URL given in the element’s value.

#####search

> One-line plain-text edit control for entering one or more search terms.

#####tel

> One-line plain-text edit control for entering a telephone number.

#####color

> Color-well control, for setting the element’s value to a string representing a simple color.

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

###Helpful links

- http://www.html5rocks.com/en/tutorials/forms/html5forms/
