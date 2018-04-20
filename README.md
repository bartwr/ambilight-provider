# ambilight-provider

## Description

Ambilight-provider is a module, which when running, is generating a RGB integer array, representing the dominant color of the screen.
The color is calculated every given Millisecond, based on the value given in the 'interval' parameter, in the start function.

Initial purpose of the module, was to sync wifi bulbs, with the movie running on a media server.
Best tested interval without failure is currently 150ms, but surely depends on processor speed, etc.

## Installation

```sh
$ npm install ambilight-provider --save
```

## Usage

```js
var ambilight = require("ambilight-provider")

ambilight.start(150, (color) => {
    console.log(color)
    // Ex -> [183, 67, 102, 1] <-> [Red, Green, Blue, Hue]
})

setTimeout(() => {
    ambilight.stop()
    console.log("stopped ambilight")
}, 3000)
```

### Functions

#### `ambilight.on(interval, callback)`
This starts the module.

Params | Type | Default | Description
------ | ---- | ------- | -----------
`interval` | int | null | The desired time(Milliseconds) between each calculation of ambilight color.
`callback` | function | null | `function(color)` An RGB value is generated as [x, x, x], and must be handled in this function (see example)

#### `ambilight.stop()`

Stops the module.

#### `ambilight.isRunning()`

Returns true if module is running.
