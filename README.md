# jQuery Crayon Picker

## License

jQuery Crayon Picker licensed under the MIT License.

## Demo / Example

Access a [live demo](http://www.vmichnowicz.com/examples/crayonpicker/index.html).

## Introduction

jQuery Crayon Picker is a very simple jQuery color picker plugin for jQuery 1.4.3 and higher.

## Usage

### The Basics

Setting up jQuery Crayon Picker is very simple. Assume the following HTML text input:

````
<input type="text" name="favorite_color" id="favorite_color" />
````

The jQuery to apply the color picker to this element would look like this:

````
$('#favorite_color').crayonpicker();
````

This jQuery code above will show the color picker whenever the HTML text input gains focus. As soon as a color is selected the hex value of that color is placed into the input tag.

### Adding a Trigger

A trigger is an element that launches the color picker. Typically the color picker is run when the HTML form input gains focus. However, it can also be run when a *trigger* element is clicked. A practical application for this could be an image of a color wheel next to the form input. If you set this image of a color wheel as the trigger then whenever this image is clicked the color picker will open up.

A trigger element must be a HTML anchor element with an `href` attribute pointing to your text input. It would look similar to this:

````
<input type="text" id="colorpicker_2" />
<a href="#colorpicker_2" id="colorpicker_2_trigger">Crayon Picker Trigger</a>
````

In this example above the anchor element has a `href` attribe equal to `#colorpicker_2`. This points to the ID `colorpicker_2` of the form input above it.

Then the jQuery to instantiate the colorpicker for this trigger would be:

````
$('#colorpicker_2_trigger').crayonpicker();
````

Notice that we our jQuery selector points to the *trigger* element, **not** the form input.

## Methods

There are four available methods within jQuery Crayon Picker. All four method have the same three parameters:

 * `target` The HTML form input where the color will go
 * `trigger` The (optional) jQuery object that can also trigger the color picker to open
 * `color` The hex color value (`#fffff`, `#ff0000`, `#7f7f7f`, etc...)

### onOpen [ object *target*, object *trigger*, string *color* ]

This method runs right before the color picker is opened. The `color` parameter in this case is the current selected color. If no color has been selected yet than this parameter is `null`.

### onClose [ object *target*, object *trigger*, string *color* ]

Right before the color picker is closed this method is run.

### onSelection [ object *target*, object *trigger*, string *color* ]

On selection of a color this method is run.

### onChange [ object *target*, object *trigger*, string *color* ]

Once a new color is selected this method is run. If the user keeps on selecting the same color multiple times in a row, this method will only run once as it only runs when the selected color *changes*.