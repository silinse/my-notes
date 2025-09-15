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


### for...in loop
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



