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

// unions as function parameter
function move(direction: "north" | "south" | "east" | "west") {
  // Implementation...
}
// create type for that
type Direction = "north" | "south" | "east" | "west";

function move(direction: Direction) {
  // Implementation...
}
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

### default parameters
```
function newCharacter(name: string, role: string = "warrior"): string {
  return `${name} is a ${role}`;
}

console.log(newCharacter("Gandalf"));
// Gandalf is a warrior
console.log(newCharacter("Gandalf", "wizard"));
// Gandalf is a wizard

function countdown(start = 10): void {
  // start is a number
  console.log(`Counting down from ${start}...`);
}
```

### tempalte literal types
```
type Class = "wizard" | "warrior" | "rogue";
type Hero = `elf ${Class}`;
// same as:
type Hero = "elf wizard" | "elf warrior" | "elf rogue";

type Class = "wizard" | "warrior" | "rogue";
type Race = "elf" | "human" | "dwarf";
type Hero = `Hero: ${Race} ${Class}`;
// Hero: elf wizard | Hero: elf warrior | Hero: elf rogue | Hero: human wizard | Hero: human warrior | Hero: human rogue | Hero: dwarf wizard | Hero: dwarf warrior | Hero: dwarf rogue

//You can also create types that enforce a simple pattern match. For example:
type logRecord = `${string}: ${number}`;
// this is valid because it's a string followed by a colon and a number
const criticalErr: logRecord = "CRITICAL: 69";
// these are all invalid
const criticalErr: logRecord = "CRITICAL 92";
const criticalErr: logRecord = "CRITICAL: 92a";
const criticalErr: logRecord = "92: CRITICAL";
```


