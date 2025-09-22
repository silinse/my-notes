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
```

### maps
```
const map = new Map();
map.set("bertholdt", "shifter");
map.set("reiner", "warrior");
map.set("annie", "shifter");
map.set("bertholdt", "colossal titan");
console.log(map);
// Map { 'bertholdt' => 'colossal titan', 'reiner' => 'warrior', 'annie' => 'shifter' }

map.delete("annie");
console.log(map);
// Map { 'bertholdt' => 'colossal titan', 'reiner' => 'warrior' }
```

#### access keys and values of map
```
for (const [key, value] of myMap) {
  console.log('Key:', key);      // prints the actual object
  console.log('Value:', value);  // prints the value
}
```

### setTimeout (async)
```
console.log("I print first");
setTimeout(
  () => console.log("I print third because I'm waiting 100 milliseconds"),
  100,
);
console.log("I print second");

// Output:
// I print first
// I print second
// I print third because I'm waiting 100 milliseconds
```

### promises
```
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    if (getRandomBool()) {
      resolve("resolved!");
    } else {
      reject("rejected!");
    }
  }, 1000);
});

function getRandomBool() {
  return Math.random() < 0.5;
}

promise
  .then((message) => {
    console.log(`The promise finally ${message}`);
  })
  .catch((message) => {
    console.log(`The promise finally ${message}`);
  });

// if the promise resolves, the output will be:
// The promise finally resolved!

// if the promise rejects, the output will be:
// The promise finally rejected!
```

#### await vs .then
```
promise.then((message) => {
  console.log(`Resolved with ${message}`);
});

const message = await promise;
console.log(`Resolved with ${message}`);
```

When using await, if the promise is rejected, it will throw an error. That means we can use standard try/catch blocks to handle rejections.
```
try {
  const message = await promise;
  console.log(`Resolved with ${message}`);
} catch (error) {
  console.log(`Rejected with ${error}`);
}
```

#### new promise() vs asynic
```
// new Promise
function getPromiseForUserData() {
  return new Promise((resolve) => {
    fetchDataFromServer().then(function (user) {
      resolve(user);
    });
  });
}

const promise = getPromiseForUserData();

// await
async function getPromiseForUserData() {
  const user = await fetchDataFromServer();
  return user;
}

const promise = getPromiseForUserData();
```

