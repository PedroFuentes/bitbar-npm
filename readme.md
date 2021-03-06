# bitbar [![Build Status](https://travis-ci.org/sindresorhus/bitbar.svg?branch=master)](https://travis-ci.org/sindresorhus/bitbar)

> Simplifies [BitBar](https://github.com/matryer/bitbar) app plugin creation

Create your plugin using a nice API instead of having to manually construct a big string.

*Requires BitBar 1.4 or above.*

<img src="screenshot.png" width="232">


## Install

```
$ npm install --save bitbar
```


## Usage

```js
#!/usr/bin/env /usr/local/bin/node
const bitbar = require('bitbar');

bitbar([
	{
		text: '❤',
		color: bitbar.darkMode ? 'white' : 'red',
		dropdown: false
	},
	bitbar.sep,
	{
		text: 'Unicorns',
		color: '#ff79d7',
		href: 'https://www.youtube.com/watch?v=9auOCbH5Ns4'
	},
	bitbar.sep,
	'Ponies'
]);
```

Create a file with the above code in the BitBar plugins directory and make sure to `chmod +x filename.js` it. [Read more.](https://github.com/matryer/bitbar#installing-plugins)

*Change `/usr/local/bin/node` to the path of your Node.js binary. This is a [known issue](https://github.com/matryer/bitbar/issues/36) in BitBar.*


## API

### bitbar(items, [options])

#### items

Type: `array` of `string|object`

An item can be a string with the text or an object with the text in a `text` property and any of the `options`. The text can be multiple lines, but for the first item, only the first line will be shown in the menubar.

#### options

Type: `object`

You can use any of the [supported options](https://github.com/matryer/bitbar#plugin-api).

Applies to all items unless overridden in the item.

### bitbar.sep

Add a separator.

### bitbar.darkMode

Returns a boolean of whether OS X Dark Mode is enabled.


## License

MIT © [Sindre Sorhus](http://sindresorhus.com)
