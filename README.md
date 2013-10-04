# Wings

Flight component loader.

## Wings(modules[, targets])

#### `modules`: Object

Flight components path and config map.

Example:

```js
var modules = {
	'path/to/flight/component': {
		domReady: true,
		enabled: true,
		options: {
			color: '#fff'
		},
		selector: '#foo'
	}
};

wings(modules);
```

#### `targets`: Object

Optional. Target name and media query map. Override default config. 

```js
var targets = {
	smallscreen: 'only screen and (min-device-width: 320px) and (max-device-width: 767px)'
},

modules = {
	'path/to/flight/component': {
		domReady: true,
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
};

wings(modules, targets);
```

####

## Component.attachTo(selector[, domReady][, options])

#### `selector`: String | Element | Element collection

[See offical Flight docs](https://github.com/flightjs/flight/blob/master/doc/component_api.md#selector-string--element--element-collection)

#### `domReady`: Boolean

Optional. If true, the Component will be attached to the selected node(s) after the DOM is fully loaded.

#### `options`: Object

[See offical Flight docs](https://github.com/flightjs/flight/blob/master/doc/component_api.md#options-object)