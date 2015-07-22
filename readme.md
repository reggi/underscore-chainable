# Underscore Chainable

Allow for any object of functions to be chainable.

```bash
npm install underscore-chainable
```

## Example

```javascript
var _ = require("underscore")
_.mixin(require("underscore-chainable"))

var cat = _.makeChainable() // make the `cat` object chainable

cat.eat = function(food){
  if(food == "tuna") return 95
  if(food == "milk") return 35
  return 0
}

cat.play = function(energy){
  if(energy < 50) return 0
  return 100
}

_.extendChainable(cat) // extend the chainablity

// adds `.chain` and `.value`

var energy  = cat.eat("tuna")
var status = cat.play(energy)

console.log(status) // 100

var status = cat
  .chain("tuna")
  .eat()
  .play()
  .value()

console.log(status) // 100
```
