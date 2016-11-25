# Chartist Tooltip plugin

A chartist plugin that adds a tooltip to each point, slice or bar on your chart.

## Features
* adds a hover state (a css class) for each point, slice or bar (depending on your chart type), which can be styled according to your needs
* mouse follow for line charts to improve accessibility with support for multiple series
* css controlled animation
* horizontal collision detection (minimalistic)
* allows the use of template elements
* the value can be formatted (eg: to currency) using the option `valueTransformFunction`


## Install
If you use Bower, run `bower install chartist-plugin-tooltip2`.

Otherwise, copy `chartist-plugin-tooltip2.js` and `chartist-plugin-tooltip2.css` and add them to your page.

```javascript
var chart = new Chartist.Line('.ct-chart', {
    labels: [1, 2, 3, 4, 5, 6, 7],
    series: [
        [1, 5, 3, 4, 6, 2, 3],
        [2, 4, 2, 5, 4, 3, 6]
    ]
}, {
    plugins: [
        Chartist.plugins.tooltip2({
            // your options here (see bellow)
        })
  ]
});
```

## Options
```javascript
// the namespace css class to use for the tooltips
cssClass: 'chartist-tooltip',

// the x/y offset of the tooltip
offset: {
    x: 0,
    y: -20,
},

// Value transform function
// It receives a single argument that contains the current value
// "this" is the current chart
// It must return the formatted value to be added in the tooltip (eg: currency format)
valueTransformFunction: null,

// Use an already existing element as a template for the tooltip
// the content of the element must be a Mustache-style template
// {{value}} {{metaElement}}
elementTemplateSelector: null,

// Markup to use as a template for the content of the tooltip
template: '<p>{{meta}}: {{value}}</p>',

// The delay before hiding the tooltip after the mouse has left the point, slice or bar
hideDelay: 500,
```
