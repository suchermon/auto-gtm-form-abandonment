Automated form abandonment tracking for GTM
===========================================

Based on work by [Simo Ahava](https://github.com/sahava): http://www.simoahava.com/analytics/track-form-abandonment-with-google-tag-manager/

This script will automatically track all forms on your pages. When a user changes input values on a form, it will be tracked unless the form is the one being submitted. Form and input 'name' attributes are used by default.

See [index.html](index.html) for an example. Or setup a Tag like this:

1. Tag -> Custom HTML -> Paste [auto-ga-form-abandonment.js](auto-ga-form-abandonment.js) in
2. Trigger -> Trigger when the form you want exists then fire this tag. Example:
    - In Trigger: Dom Ready -> Some DOM Ready Events -> (Var to get form) Contains -> `'formId'`
    
```
Var - GetForm()
function() {
  	//[0] would be the search form
	return document.querySelectorAll('form')[1].id;
}
```

## Prerequisites

1. Add form submit trigger in GTM (either on all forms or the subset you want to track)
2. Add trigger for custom event 'formAbandonment'
3. Add data layer variables 'eventAction' and 'eventCategory'
4. Add tag to trigger a GA event on formAbandonment trigger with event category and action taken from data layer variables
5. Include [auto-ga-form-abandonment.js](auto-ga-form-abandonment.js) script
6. Observe form abandonment events in GA!


