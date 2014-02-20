*This repository is a mirror of the [component](http://component.io) module [treygriffith/events](http://github.com/treygriffith/events). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/treygriffith-events`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# events

  Element event management component. Allows you to unbind listeners by event type , or unbind every listener from an element.
  It can work as a single global instance for managing all application events, but it's preferable to use it within another object that attaches events to elements, such as a template/view.

## Installation

    $ component install treygriffith/events

See http://github.com/component for more information

## Example

```js
var Events = require('events');
var events = new Events();
var a = document.querySelector('a');

var onclick = function () {
  e.preventDefault();
  console.log(e.target);
};

events.bind(a, 'click', function () {
  e.preventDefault();
  console.log(e.target);
});

events.bind(a, 'click', onclick);

events.bind(a, 'dblclick', function () {
  e.preventDefault();
  console.log(e.target);
});

events.bind(a, 'dblclick', function () {
  e.preventDefault();
  console.log(e.target + "2");
});

events.unbind(a, 'click', onclick); // removes only the onclick listener
events.unbind(a, 'dblclick'); // remove all the `dblclick` listeners
events.unbind(a); // remove all event listeners

```

## API

### .bind(el, type, callback)

  Bind to `el`'s event `type` with `callback`,
  returns the `callback` passed.

### .unbind(el, type, callback)

  Unbind events from `el`, optionally specified by `type` and `callback`,
  returns an array of unbound callbacks

## License

  MIT