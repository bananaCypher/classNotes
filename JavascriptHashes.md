# Javascript Hashes

## What is a hash
A hash is a key value pair, a hash in Javascript is an object.

## Hash basics
When to use certain ways to access a Hash
### Dot notation
```javascript
var myPerson = {
    name: 'Guybrush',
    age: 32,
    weapon: 'cutlass'
};

console.log(myPerson.name);
```
```bash
Guybrush
```

### String notation
The string used to get the value can be taken from a variable allowing more flexability than the dot notation
```javascript
var myPerson = {
    name: 'Guybrush',
    age: 32,
    weapon: 'cutlass'
};

console.log(myPerson['name']);
```
```bash
Guybrush
```


### Dynamically adding values
```javascript
var myPerson = {
    name: 'Guybrush',
    age: 32,
    weapon: 'cutlass'
};
myPerson.location = "california";
console.log(myPerson.location);
myPerson["location"] = "edinburgh";
console.log(myPerson.location);
```
```bash
california
edinburgh
```
