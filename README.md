# Wings

Opinionated Flight component loader.

## Wings(modules[, targets])

#### `modules`: Object

Component module path and config map.

Use:

```js
require(

	[
		'path/to/wings'
	],
	
	function (wings) {

		var modules = {
			'path/to/your/flight/component': {
				enabled: true,
				options: {},
				selector: document
			}
			[, another component to load]
			[, another component to load]
			[, ... ]
		};

		wings(modules);
	}
);
```

Example: Define component selector and options

```js
'path/to/your/flight/component': {
	options: {
		color: '#fff'
	},
	selector: '#foo'
}
```
Example: Prevent a component from being loaded

```js
'path/to/your/flight/component': {
	enabled: false
}
```
Or

```js
'path/to/your/flight/component': false
```

#### `targets`: Object

Optional. Target name and media query map. Override default module config per target.

Use:

```js
var targets = {
	smallscreen: 'only screen and (min-device-width: 320px) and (max-device-width: 767px)'
};

wings(modules, targets);
```

Example:

```js
'path/to/your/flight/component': {
	options: {
		color: '#fff'
	},
	selector: '#foo',
	smallscreen: {
		domReady: false,
		options: {
			color: '#000'
		},
		selector: '#boo'
	}
}
```

Example: 

```js
'path/to/your/flight/component': {
	smallscreen: {
		options: {
			color: '#000'
		},
		selector: '#boo'
	}
}
```

####

## Component.attachTo(selector[, domReady][, options])

#### `selector`: String | Element | Element collection

[See offical Flight docs](https://github.com/flightjs/flight/blob/master/doc/component_api.md#selector-string--element--element-collection)

#### `domReady`: Boolean

Optional. If true, the Component will be attached to the selected node(s) after the DOM is fully loaded.

#### `options`: Object

[See offical Flight docs](https://github.com/flightjs/flight/blob/master/doc/component_api.md#options-object)

Example: Attach component to '#foo' only after DOM is ready

```js
'path/to/your/wings/component': {
	domReady: true,
	options: {
		color: '#fff'
	},
	selector: '#foo'
}
```