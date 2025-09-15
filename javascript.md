# javascript stuff

## basic commands

### print to console
`console.log("hello there!");`

### anonymous functions
```
conversions(
  function (a) {
    return a + a;
  },
  1,
  2,
  3,
);
// 2 4 6
```

### define object
```
const fruit = {
    name: "apple",
    color: "red",
}
```

### fat arrow function
```
const add = (x, y) => {
  return x + y;
}
```


### for loop
```
for (let i = 0; i < 5; i++) {
  console.log(i);
}
// 0
// 1
// 2
// 3
// 4
```


### for...in loop (used to loop over the keys of an object)
```
let titan = {
  name: "Eren",
  power: "Attack Titan",
  age: 19,
};

for (const key in titan) {
  console.log(`${key}: ${titan[key]}`);
}
// name: Eren
// power: Attack Titan
// age: 19
```

### for...of (loop over array)
```
let woods = ["oak", "pine", "maple"];
for (let wood of woods) {
  console.log(wood);
}
// prints:
// oak
// pine
// maple
```

### destructing arrays
```
const nums = [1, 2, 3, 4, 5];
const [a, b, ...restOfThem];
// a == 1
// b == 2
// restofThem == [3, 4, 5]
