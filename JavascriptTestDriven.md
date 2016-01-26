# Test Driven Javascript

## Installing mocha test suite
```bash
npm install -g mocha

/usr/local/bin/_mocha -> /usr/local/lib/node_modules/mocha/bin/_mocha
/usr/local/bin/mocha -> /usr/local/lib/node_modules/mocha/bin/mocha
/usr/local/lib
└─┬ mocha@2.3.4 
  ├── commander@2.3.0 
  ├─┬ debug@2.2.0 
  │ └── ms@0.7.1 
  ├── diff@1.4.0 
  ├── escape-string-regexp@1.0.2 
  ├─┬ glob@3.2.3 
  │ ├── graceful-fs@2.0.3 
  │ ├── inherits@2.0.1 
  │ └─┬ minimatch@0.2.14 
  │   ├── lru-cache@2.7.3 
  │   └── sigmund@1.0.1 
  ├── growl@1.8.1 
  ├─┬ jade@0.26.3 
  │ ├── commander@0.6.1 
  │ └── mkdirp@0.3.0 
  ├─┬ mkdirp@0.5.0 
  │ └── minimist@0.0.8 
  └── supports-color@1.2.0 
```


## Get mocha version
```bash
mocha -V
2.3.4
```

## Writing tests
First thing you need is a test spec file e.g. for water_bottle.js water_bottle_spec.js is good.  In the spec file you need to require the file you want to test along with assert which comes with mocha.
```javascript
var bottle = require('./water_bottle');
var assert = require('assert');
```
Next you need to specify a describe which takes the Description of what you are describing and a function.
```javascript
describe('Water bottle', function(){

});
```
After this you start defining the actual tests, they are in the format it(description, function) e.g.
```javascript
var bottle = require('./water_bottle');
var assert = require('assert');

describe('Water bottle', function(){
    it('should be empty at start', function(){
        assert.equal(0, bottle.volume);
    });
});
```
You can then build up a full site like the below
```javascript
\\ water_bottle.js
var waterBottle = {
    volume: 0,
    fill: function(){
        this.volume = 100;
    },
    drink: function(){
        this.volume -= 10;
        if (this.volume < 0) { this.volume = 0; }
    },
    empty: function(){
        this.volume = 0;
    },
}

module.exports = waterBottle;
```
```javascript
\\ water_bottle_spec.js
var bottle = require('./water_bottle');
var assert = require('assert');

describe('Water bottle', function(){
    it('should be empty at start', function(){
        assert.equal(0, bottle.volume);
    });
    it('should go to 100 when filled', function(){
        bottle.fill();
        assert.equal(100, bottle.volume);
    });
    it('should go down by 10 when drunk', function(){
        bottle.drink();
        assert.equal(90, bottle.volume); 
    });
    it('should go to 0 when emptied', function(){
        bottle.empty();
        assert.equal(0, bottle.volume);
    });
    it('should not be able to go below 0', function(){
        bottle.drink();
        assert.equal(0, bottle.volume);
    });
});
```


## Running tests
Tests are run by using the `mocha` command.
```bash
mocha water_bottle_spec.js
```
```bash


  Water bottle
    ✓ should be empty at start
    ✓ should go to 100 when filled
    ✓ should go down by 10 when drunk
    ✓ should go to 0 when emptied
    ✓ should not be able to go below 0


  5 passing (9ms)

```
