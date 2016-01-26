# Javascript Objects
* [Basics](#basics)
* [How do they differ to Ruby Objects](#how-do-they-differ-to-ruby-objects)
* [Adding properties to objects](#adding-properties-to-objectss)
* [Adding functions to objects](#adding-functions-to-objects)
* [Instance variables](#instance-variables)
* [Setting up objects inline](#setting-up-objects-inline)


## Basics
In Javascript, hashes are objects thay are key-pairs and methods are just another key-pair.  An object contains properties which can be read and updated and a list of methods/functions that can be run against it.

## How do they differ to Ruby Objects
Javascript doesn't use classes like Ruby, objects are created individually rather than using a .new notation.  Ruby is almost like a Class based language while Javascript is a true Object orientated language.

## Adding properties to objects
Properties are added just as you would a hash in { brackets and in the form key:value
```javascript
var myPerson = {
    name: 'Guybrush',
    age: 32,
    weapon: 'cutlass',
}

console.log(myPerson.name);
```
```bash
Guybrush
```

## Adding functions to objects
To add a function to an object just set one of it's properties to a function like so
```javascript
var myPerson = {
    name: 'Guybrush',
    age: 32,
    weapon: 'cutlass',
    talk: function(){
        console.log('shiver me timbers')
    }
}

myPerson.talk();
```
```bash
shiver me timbers
```

## Instance variables
Instance variables are accessed using the this. notation like below
```javascript
var myPerson = {
    name: 'Guybrush',
    age: 32,
    weapon: 'cutlass',
    talk: function(){
        console.log('shiver me timbers, my name is ' + this.name);
    }
}

myPerson.talk();
```
```bash
shiver me timbers, my name is Guybrush
```


## Setting up objects inline
Objects can be built up inline without having to pre-specify functions and attributes
```javascript
var myDog = {};
myDog.smell = 'musky';
console.log(myDog);
myDog.talk = function (){
    console.log("I am a dog and I smell " + this.smell);
}
myDog.talk();
```
```bash
{ smell: 'musky' }
I am a dog and I smell musky
```
