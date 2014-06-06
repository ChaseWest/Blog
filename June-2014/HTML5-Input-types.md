#HTML5 Input Types

  All types are viewable [here](http://jsfiddle.net/ChaseWest/4pFmg/).

  HTML5 introduces many new additions, a small fraction of which are new `input` types. First, lets review the current types provided prior:

###Old Types

| Type  | Contains  | Control | 
| ------------- | ------------- | ------------- |
| [**text**](http://www.w3.org/TR/html-markup/input.text.html#input.text)  | Text with no line breaks  | One-line plain-text edit control for the input element’s value.  |
| [**password**](http://www.w3.org/TR/html-markup/input.password.html)  | Text with no line breaks (sensitive information)  | One-line plain-text edit control for entering a password.  |
| [**checkbox**](http://www.w3.org/TR/html-markup/input.checkbox.html)  | A set of zero or more values from a predefined list  | Represents a state or option that can be toggled.  |
| [**radio**](http://www.w3.org/TR/html-markup/input.radio.html)  | An enumerated value  | Represents a selection of one item from a list of items.   |
| [**button**](http://www.w3.org/TR/html-markup/input.button.html)  | N/A  | Button with no additional semantics.  |
| [**submit**](http://www.w3.org/TR/html-markup/input.submit.html)  | Button for submitting a form.  | An enumerated value, with the extra semantic that it must be the last value selected and initiates form submission.  |
| [**reset**](http://www.w3.org/TR/html-markup/input.reset.html)  | N/A  | Button for resetting a form.  |
| [**file**](http://www.w3.org/TR/html-markup/input.file.html)  | Represents a list of file items.  | Zero or more files each with a MIME type and optionally a file name.  |
| [**hidden**](http://www.w3.org/TR/html-markup/input.hidden.html)  | An arbitrary string  | Represents a value that is not intended to be examined or manipulated by the user.  |
| [**image**](http://www.w3.org/TR/html-markup/input.image.html)  | A coordinate, relative to a particular image's size, with the extra semantic that it must be the last value selected and initiates form submission  | Either an image from which the UA enables a user to interactively select a pair of coordinates and submit the form, or alternatively a button from which the user can submit the form.  |



###New Types

*Note: If the browser does not support the given type it will revert to using a type of `text`*

| Type  | Contains  | Control | 
| ------------- | ------------- | ------------- |
| [**datetime**](http://www.w3.org/TR/html-markup/input.datetime.html)  | A date and time (year, month, day, hour, minute, second, fraction of a second) with the time zone set to UTC  | Control for setting the element’s value to a string representing a global date and time. | 
| [**datetime-local**](http://www.w3.org/TR/html-markup/input.datetime-local.html)  | A date and time (year, month, day, hour, minute, second, fraction of a second) with no time zone  | Control for setting the element’s value to a string representing a local date and time. | 
| [**date**](http://www.w3.org/TR/html-markup/input.date.html)  | A date (year, month, day) with no time zone  | Control for setting the element’s value to a string representing a date. | 
| [**month**](http://www.w3.org/TR/html-markup/input.month.html)  | A date consisting of a year and a month with no time zone  | Control for setting the element’s value to a string representing a month. | 
| [**time**](http://www.w3.org/TR/html-markup/input.time.html)  | A time (hour, minute, seconds, fractional seconds) with no time zone  | Control for setting the element’s value to a string representing a time. |
| [**week**](http://www.w3.org/TR/html-markup/input.week.html)  | A date consisting of a week-year number and a week number with no time zone  | Control for setting the element’s value to a string representing a week. |
| [**number**](http://www.w3.org/TR/html-markup/input.number.html)  | A numerical value  | Precise control for setting the element’s value to a string representing a number. |
| [**range**](http://www.w3.org/TR/html-markup/input.range.html)  | A numerical value, with the extra semantic that the exact value is not important  | Imprecise control for setting the element’s value to a string representing a number. |
| [**email**](http://www.w3.org/TR/html-markup/input.email.html)  | An e-mail address or list of e-mail addresses  | Control for editing an e-mail address or list of e-mail addresses given in the element’s value. |
| [**url**](http://www.w3.org/TR/html-markup/input.url.html)  | An absolute IRI  | Control for editing an absolute URL given in the element’s value. |
| [**search**](http://www.w3.org/TR/html-markup/input.search.html)  | Text with no line breaks  | One-line plain-text edit control for entering one or more search terms. |
| [**tel**](http://www.w3.org/TR/html-markup/input.tel.html)  | Text with no line breaks  | One-line plain-text edit control for entering a telephone number. |
| [**color**](http://www.w3.org/TR/html-markup/input.color.html)  | An sRGB color with 8-bit red, green, and blue components  | Color-well control, for setting the element’s value to a string representing a simple color. |



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
