# ambilight-provider

## Description

Description

## Installation

```sh
$ npm -i ambilight-provider --save
```

## Usage

```js
var ambilight = require("ambilight-provider")

ambilight.start(150, (color) => {
    console.log(color)
})

setTimeout(() => {
    ambilight.stop()
    console.log("stopped ambilight")
}, 3000)
```

### Functions

#### `ambilight.on(interval, callback)`
This starts the service

Params | Type | Default | Description
------ | ---- | ------- | -----------
`interval` | int | 0 | Turning on will be faded over the time (in milliseconds).
`callback` | function | null | `function(color)` An RGB value is generated as [x, x, x], and mus tbe handled in this function (see example)

#### `ambilight.stop()`

Stops the service, if it is running.

#### `ambilight.isRunning()`

Returns true if service is running.
