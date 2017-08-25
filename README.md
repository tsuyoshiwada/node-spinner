# @tsuyoshiwada/node-spinner

A simple spinner for node cli.

> It is the fork version of `node-spinner`. Color designation has been added :tada:

## Installation

This package is available on [npm](http://npmjs.com) as `@tsuyoshiwada/cli-spinner`.

``` sh
npm install @tsuyoshiwada/cli-spinner --save
```

## Example usage

````javascript
var Spinner = require('@tsuyoshiwada/cli-spinner').Spinner;

var spinner = new Spinner('processing.. %s');
spinner.setSpinnerString('|/-\\');
spinner.start();
````

## APIs

```
var obj = new Spinner('processing.. %s')

var obj = new Spinner({
    text: 'processing.. %s',
    color: 'cyan',
    stream: process.stderr,
    onTick: function(msg){
        this.clearLine(this.stream);
        this.stream.write(msg);
    }
})
```

Create a new spinner object. The advanced options can be used in any combination, none of them are required.


**`obj.start()`**

Starts the spinner.


**`obj.stop(clean)`**

Stops the spinner. Accepts a Boolean parameter to clean the console.


**`obj.setSpinnerString(spinnerString)`**

Sets the spinner string. Accepts either a String or an Integer index to reference the [built-in spinners](#demo).


**`obj.setSpinnerDelay(spinnerDelay)`**

Sets the spinner animation speed.


**`Spinner.setDefaultSpinnerString(spinnerString)`**

Sets the default spinner string for all newly created instances. Accepts either a String or an Integer index to reference the [built-in spinners](#demo).


**`Spinner.setDefaultSpinnerDelay(spinnerDelay)`**

Sets the default spinner delay for all newly created instances.


**`Spinner.setSpinnerTitle(spinnerTitle)`**

Sets the spinner title. Use printf-style strings to position the spinner.


**`Spinner.setSpinnerColor(color)`**

Sets the spinner color. Please specify the color name as a character string. Using [chalk](https://github.com/chalk/chalk); (Default: `null`)


**`Spinner.isSpinning()`**

Returns true/false depending on whether the spinner is currently spinning.

## Demo

To see a demonstration of the built-in spinners.

```bash
$ node example/spinner.js
```

![preview](img/spinner.gif "Spinner")
