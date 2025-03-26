# Javascript Quest

##  Chain calculator
A chain calculator in JavaScript refers to a function or an object that supports method chaining, allowing multiple operations to be performed sequentially on a single instance without breaking the flow. It improves code readability and efficiency by returning this (the object itself) after each method call, enabling further operations.

Example: Simple Chainable Calculator
Key Concepts:
- Use a class to store and manipulate a value.
- Return this in each method for chaining.
- Provide methods for basic arithmetic operations.

```js
class ChainCalculator {
  constructor(value = 0) {
    this.value = value;
  }
  add(num) {
    this.value += num;
    return this;
  }
  subtract(num) {
    this.value -= num;
    return this;
  }
  multiply(num) {
    this.value *= num;
    return this;
  }
  divide(num) {
    if (num !== 0) this.value /= num;
    return this;
  }
  result() {
    return this.value;
  }
}

// Usage:
const calc = new ChainCalculator();
const output = calc.add(10).subtract(2).multiply(3).divide(2).result();
console.log(output); // 12
```

## Promises in sequence

## Pipe and compose

Pipe and Compose are functional programming techniques in JavaScript that allow chaining multiple functions together to transform data in a clean and readable way. Both take multiple functions as input and execute them sequentially, but with a key difference:

Pipe executes functions left to right (first to last).

Compose executes functions right to left (last to first).

Example: Simple Pipe and Compose
Key Concepts:
- Pipe (pipe): Functions are executed in the order they are written.

- Compose (compose): Functions are executed from the last one to the first.

Use the spread operator (...fns) to take multiple functions as arguments.


4. Array polyfills
5. Prototype and prototype inheritance
6. Call, apply, bind
7. Flatten Array
8. Basic Debouncing 9 Basic Throttling
10. Event emitter
11. Debouncing leading and trailing spaces 12 MapLimit
13. Cancelable Promise
14. TypeHead search using LRU cache
15. Doc comparison
16. Currying
17. Execute task in parallel
18. Find the matching element in the DOM
19. Sort Array
20. Object Flatten
21. Array] Dispatch event on push
22. Deep clone object
23. JSON.stringify
24. React DOM render
25. Retry promises N times
26. Extended version of Event emitter
27. Promise.all
28. Promise.race 29 Promise.any
30. Promise.allSettle
31. ClearAllTimeout 32 Memoization
33. Async Progress bar 34 GroupBy Polyfill Loadsh
34. single and double click handlers