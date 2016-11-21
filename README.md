# Stepper #
- A jQuery widget for incrementing & decrementing values in an input with plus and minus buttons 

### Usage ###
We initialize this way to emulate the way a jQuery Widget would create an instance of itself for each element in the selector. Access the menu object once instantiated using ```$('.element').data('melodeon')```.

```js
// Options is an optional parameter, see the defaults below
jQuery('.stepper-widget').stepper();
```


### Options

* `identifier` **default: stepper** Used as the event namespace identifier and the element's data attribute name
* `upSelector` **default: '.js-qty-up'** The selector used for the up button
* `downSelector` *default: '.js-qty-down'* The selector used for the down button
* `inputSelector` **default: 'js-melodeon-hide'** The selector used for the input field
* `disabledClass` **default: true** The disabled class to apply to the elements when disable() is called on the widget
* `minQty` **default: true** The minimum quantity the widget will count to
* `maxQty` **default: 999** The maximum quantity the widget will count to
* `step` **default: 1** The incrememt / decrememnt step value



### Methods ###

* `enable` Enables the widget
* `disable` Disables the widget
* `updateQuantity(value)`  Updates the widget with the quantity set. This is validated against min / max values
* `stepQuantity(value)` Increment the quantity by the value specified. Use a negative number to decrement the value
* `getValue()` Returns the value held by the widget. Use this instead of getting the value from the widget's input as this value will have been passed through the validation routines 

### Callbacks ###

**update**
```js
 jQuery('.stepper-widget').on('stepperupdate', function(ev, data){
    console.log(data.updateMode);
});
```
* Use the *updateMode* parameter to check whether the widget's current value has changed from its initial value. Possible values are **same_value_entered** and **different_value_entered** 
