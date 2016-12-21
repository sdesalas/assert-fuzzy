# assert-fuzzy
Fuzzy logic assertions for nodejs `assert`.

```
var assert = require('assert-fuzzy');

assert.around(59.4, 60); // true
assert.around(72, 60); // false
```

Use it for writing tests when your assertions require approximate figures.

```
var assert = require('assert-fuzzy');

describe('class Thermometer', function() {
  it('#getTemperature()', function() {
    assert.around(Thermometer.getTemperature(), 20); // its around 20 degrees in the room
  });
});

describe('class Barometer', function() {
  it('#getPressure()', function() {
    assert.between(Barometer.getATM(), 0.9, 1.1); // its around 1 atmospheric unit of pressure in the room
  });
});

```
