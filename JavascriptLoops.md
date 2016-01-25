# Loops

## Playing around
```javascript
var pets = ["dog", "cat", "pika", "mongoose"];
var person = {
    name: "Oscar",
    age: 19
}

for (var i = 0; i < pets.length; i++) {
    console.log(pets[i]);
}

for (pet in pets) {
    console.log(pets[pet]);
}

for (var prop in person) {
    console.log(prop + " = " + person[prop]);
}

var x = 0;
while (x < 10) {
    console.log("loop " + x);
    x = x + 1;
}
```
```bash
dog
cat
pika
mongoose
dog
cat
pika
mongoose
name = Oscar
age = 19
loop 0
loop 1
loop 2
loop 3
loop 4
loop 5
loop 6
loop 7
loop 8
loop 9
```
