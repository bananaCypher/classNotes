# Javascript
## Contents
* [Uses](#uses)
* [Installing Node](#installing-node)
* [Functions](#functions)
* [Running Node scripts](#running-node-scripts)
* [Node runtime enviroment](#node-runtime-enviroment)
* [Types](#types)
* [Variables](#variables)
* [If statements](#if-statements)

## Uses
Javascript is primarily used for generating HTML and runnign in the browser but can be used to make mobile apps and has a server side interpreter called NodeJS

## Installing Node
### Doing the install
```bash
brew install node

==> Downloading https://homebrew.bintray.com/bottles/node-5.1.0.yosemite.bottle.tar.gz
==> Pouring node-5.1.0.yosemite.bottle.tar.gz
==> Caveats
Please note by default only English locale support is provided. If you need
full locale support you should:
  "brew reinstall node --with-full-icu"

Bash completion has been installed to:
  /usr/local/etc/bash_completion.d
==> Summary
🍺  /usr/local/Cellar/node/5.1.0: 2827 files, 36M
```

### Get Node version
```bash
node -v
v5.1.0
```

## Functions
### Defining functions
Functions are marked out by the function keyword, the next word is the name of the function used to call it and parameters are passed into the brackets.  This function will just take in a name and print out the name and "you are awesome!" to the console.
```javascript
function hello(name){
    console.log(name + " you are awesome!");
}
```

### Calling functions
Functions are called simply by writing the name of the function followed by curly brackets(they are required but can be empty)
```javascript
hello("Keith");
```

## Running Node scripts
```bash
node app.js

Keith you are awesome!
```

## Node runtime enviroment
### Starting the node runtime enviroment
```bash
node
```

### Running commands
```javascript
> typeof(2);
'number'
> typeof(1.1);
'number'
> typeof(-1)
'number'
> 2 + 3;
5
> 10 - 7;
3
> 2 * 4;
8
> 4 / 2;
2
> 5 /2;
2.5
> 4 % 2;
0
```

## Types
### Strings
console play
```javascript
> var name = "valerie";
undefined
> typeof(name);
'string'
> name.length;
7
> "valerie loves ".concat("cats");
'valerie loves cats'
> "valerie loves " + "cats";
'valerie loves cats'
> "keith,jay".split(",");
[ 'keith', 'jay' ]
> "route" + 6 + 6;
'route66'
> 6 + 6 + "route";
'12route'
> "route" + (6 + 6);
'route12'
```

### Boolean
console play
```javascript
> typeof(true);
'boolean'
> typeof(false);
'boolean'
> 1 > 2;
false
> 2 == 2;
true
> 2 == "2";
true
> 2 === "2";
false
> 3 != 4;
true
> (1+1 === 2);
true
> (1+1 === 2) && (1+1 ===4);
false
> (1+1 === 2) || (1+1 ===4);
true
> !(1+1 === 2);
false
```
== compares but not by type, === compares by type.
```javascript
> if(true) console.log('true');
true
undefined
> if(false) console.log('true');
undefined
> if(5) console.log('true');
true
undefined
> if(0) console.log('true');
undefined
> if("hello") console.log('true');
true
undefined
> if("") console.log('true');
undefined
> if(null) console.log('true');
undefined
> if(undefined) console.log('true');
undefined
```
Falsey, truthy acts different to Ruby. 0 and empty strings are Falsey while numbers and strings are Truthy

### Undefined
console play
```javascript
> var b;
undefined
> typeof(b);
'undefined'
```

### NaN
console play
```javascript
> if(NaN) console.log('true');
undefined
> isNaN(1);
false
> isNaN(parseInt('cat'));
true
> isNaN('hello');
true
> isNaN(0);
false
```

## Arrays
```javascript
var guitars = ["fender", "gibson", "gretsch"];
console.log(guitars);

var drums = new Array();
drums.push("gresch");
drums.push("yamaha");
console.log(drums);
console.log(drums[0]);

drums.push("bongo");
console.log(drums[2]);

drums[0] = "zildijan";
console.log(drums[0]);

drums[10] = "steel";
console.log(drums);

console.log(typeof(drums[5]));

console.log(drums.length);
```
```bash
[ 'fender', 'gibson', 'gretsch' ]
[ 'gresch', 'yamaha' ]
gresch
bongo
zildijan
[ 'zildijan', 'yamaha', 'bongo', , , , , , , , 'steel' ]
undefined
11
```

## Variables
### Using variables
console play
```javascript
> var x = 1;
undefined
> x;
1
> var y = 3;
undefined
> var z = x + y;
undefined
> z;
4
```

### Statically typed
Javascript variables are statically typed meaning that they can be set to different types
```javascript
> var number = 1;
undefined
> number = "a string";
'a string'
```

### Working with different types
Javascript will try and convert types to what is required.
```javascript
> 3 + "hello";
'3hello'
```

## If statements
Simple if statement
```javascript
var myName = "Keith";

if (myName === "Keith") {
    console.log("Hey it's Keith");
}
```
```bash
Hey it's Keith
```

### If with else statement
```javascript
var counter = 1;
if (counter > 0) {
    console.log("The counter is greater than 0");
} else {
    console.log("The counter is less than 0");
}
```
```bash
The counter is greater than 0
```

### If else statement
```javascript
var counter = 1;
if (counter > 0) {
    console.log("The counter is greater than 0");
} else if(counter < 0) {
    console.log("The counter is less than 0");
} else {
    console.log("The counter is 0");
}
```
```bash
The counter is greater than 0
```

### Switch-case statements
```javascript
var pet = "cat";
switch(pet) {
    case "cat":
        console.log("Soft kitty, warm kitty, little ball of fur.");
        break;
    case "dog":
        console.log("Who let the dogs out!");
        break;
    default:
        console.log("Not pet, sad.");
}
```
```bash
Soft kitty, warm kitty, little ball of fur.
```

### Ternary Operator
```javascript
1 + 1 === 2 ? console.log("yay, javascript can do maths") : console.log("nope js is broken");
```
```bash
yay, javascript can do maths
```
