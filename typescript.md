# typescript stuff

### print to console
```
const msg: string = "Hello there";
console.log(msg);
```

### functions
```
function createMessage(name: string, a: number, b: number): string {
  return `${name} scored ${a + b}`;
}

// arrow function
const createMessage = (name: string, a: number, b: number): string => {
  return `${name} scored ${a + b}`;
};

// return type can be inferred
const createMessage = (name: string, a: number, b: number) => {
  return `${name} scored ${a + b}`;
};
```

### type alias
```
function setLoggerTimeout(
  loggerCallback: (s1: string, s2: string) => string,
  delay: number,
) {
  // do something
}

type LoggerCallback = (s1: string, s2: string) => string;

function setLoggerTimeout(loggerCallback: LoggerCallback, delay: number) {
  // do something
}
```

### unions
```
// | allows for one of multiple types "type narrowing"
function safeSquare(val: string | number): number {
  if (typeof val === "string") {
    val = parseInt(val, 10);
  }
  // now val is only a number
  return val * val;
}

let result = safeSquare("5");
console.log(result);
// 25

result = safeSquare(5);
console.log(result);
// 25
```

### optional parameters
```
function greet(name: string, title?: string): string {
  if (title) {
    return `Hello, ${title} ${name}!`;
  }
  return `Hello, ${name}!`;
}

greet("Gandalf");           // "Hello, Gandalf!"
greet("Gandalf", "Wizard"); // "Hello, Wizard Gandalf!"
```

