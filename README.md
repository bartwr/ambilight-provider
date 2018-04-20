# ambilight-provider

## Description

Ambilight-provider is a module, which when running, is generating a RGB integer array, representing the dominant color of the screen.
The color is calculated every given Millisecond, based on the value given in the 'interval' parameter, in the start function.

Initial purpose of the module, was to sync wifi bulbs, with the movie running on a media server.
Best tested interval without failure is currently 150ms, but surely depends on processor speed, etc.

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