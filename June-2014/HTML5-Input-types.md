#HTML5 Input Types

  All types are viewable [here](http://jsfiddle.net/ChaseWest/4pFmg/);

  HTML5 introduces many new additions, a small fraction of which are new `input` types. First, lets review the current types provided prior:

###Old Types
------

#####text

> One-line plain-text edit control for the input element’s value.

Text with no line breaks

#####password

> One-line plain-text edit control for entering a password.

Text with no line breaks (sensitive information)

#####checkbox

> Represents a state or option that can be toggled.

A set of zero or more values from a predefined list

#####radio

> Represents a selection of one item from a list of items. 

An enumerated value

#####button

> Button with no additional semantics.

#####submit

> Button for submitting a form. 

An enumerated value, with the extra semantic that it must be the last value selected and initiates form submission

#####reset

> Button for resetting a form.

#####file

> Represents a list of file items.

Zero or more files each with a MIME type and optionally a file name

#####hidden

> Represents a value that is not intended to be examined or manipulated by the user.

An arbitrary string

#####image

> Either an image from which the UA enables a user to interactively select a pair of coordinates and submit the form, or alternatively a button from which the user can submit the form.

A coordinate, relative to a particular image's size, with the extra semantic that it must be the last value selected and initiates form submission

###New Types
------

*Note: If the browser does not support the given type it will revert to using a type of `text`*

#####datetime

> Control for setting the element’s value to a string representing a global date and time.

A date and time (year, month, day, hour, minute, second, fraction of a second) with the time zone set to UTC

#####datetime-local

> Control for setting the element’s value to a string representing a local date and time.

A date and time (year, month, day, hour, minute, second, fraction of a second) with no time zone

#####date

> Control for setting the element’s value to a string representing a date.

A date (year, month, day) with no time zone

#####month

> Control for setting the element’s value to a string representing a month.

A date consisting of a year and a month with no time zone

#####time

> Control for setting the element’s value to a string representing a time.

A time (hour, minute, seconds, fractional seconds) with no time zone

#####week

> Control for setting the element’s value to a string representing a week.

A date consisting of a week-year number and a week number with no time zone

#####number

> Precise control for setting the element’s value to a string representing a number.

A numerical value

#####range

> Imprecise control for setting the element’s value to a string representing a number.

A numerical value, with the extra semantic that the exact value is not important

#####email

> Control for editing an e-mail address or list of e-mail addresses given in the element’s value.

An e-mail address or list of e-mail addresses

#####url

> Control for editing an absolute URL given in the element’s value.

An absolute IRI

#####search

> One-line plain-text edit control for entering one or more search terms.

Text with no line breaks

#####tel

> One-line plain-text edit control for entering a telephone number.

Text with no line breaks

#####color

> Color-well control, for setting the element’s value to a string representing a simple color.

An sRGB color with 8-bit red, green, and blue components

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
- http://www.w3.org/wiki/HTML/Elements/input
- http://www.w3.org/TR/html-markup/input.html
