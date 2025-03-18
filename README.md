# Superior Javascript

- 1- What is OOP
- 2- Four Pillars of OOP
- 3- Setting Up the Development Environment
- 4- Course Structure

Objects 
- 1- Introduction
- 2- Object Literals
- 3- Factories
- 4- Constructors
- 5- Constructor Property
- 6- Functions are Objects
- 7- Value vs Reference Types
- 8- Adding or Removing Properties
- 9- Enumerating Properties
- 10- Abstraction
- 11- Private Properties and Methods
- 12- Getters and Setters

Prototypes 

- 1- Inheritance
- 2- Prototypes and Prototypical Inheritance
- 3- Multilevel Inheritance
- 4- Property Descriptors
- 5- Constructor Prototypes
- 6- Prototype vs Instance Members
- 7- Iterating Instance and Prototype Members
- 8- Avoid Extending the Built-in Objects

Prototypical Inheritance 
- 1- Creating Your Own Prototypical Inheritance
- 2- Resetting the Constructor
- 3- Calling the Super Constructor
- 4- Intermediate Function Inheritance
- 5- Method Overriding
- 6- Polymorphism
- 7- When to Use Inheritance
- 8- Mixins

ES6 Classes 

- 1- ES6 Classes
- 2- Hoisting
- 3- Static Methods
- 4- The This Keyword
- 5- Private Members Using Symbols
- 6- Private Members Using WeakMaps
- 7- Getters and Setters
- 8- Inheritance
- 9- Method Overriding

ES6 Tooling 
- 1- Modules
- 2- CommonJS Modules
- 3- ES6 Modules
- 4- ES6 Tooling
- 5- Babel
- 6- Webpack




# Object-Oriented Programming
Object-Oriented Programming (OOP) is a programming approach that organizes code into objects, which represent real-world entities with data (attributes) and behaviors (methods). Instead of writing long procedural code, OOP structures programs using classes (blueprints) that create reusable objects. The four main principles of OOP—Encapsulation, Inheritance, Polymorphism, and Abstraction—help in keeping code modular, reusable, and easy to maintain. This approach solves issues like code duplication, security risks, and scalability by ensuring that different parts of a program are independent yet interconnected in a structured way.

### Key Benefits of OOP:
- Reusability → Write once, reuse multiple times with classes & inheritance.
- Maintainability → Organized code is easier to debug & update.
- Scalability → Easily add new features without breaking old ones.
- Encapsulation → Keeps data secure by restricting access.
- Polymorphism → Use a single interface for different types of objects.
- Abstraction → Hides complex details, showing only necessary features.

### How OOP Solves the Spaghetti Code Problem in Procedural Programming:
Procedural programming often leads to spaghetti code, where functions and variables are scattered across the program without clear organization. As the codebase grows, it becomes hard to read, debug, and modify, since everything is tightly coupled and dependent on execution order. OOP solves this by structuring code into objects, encapsulating data and behaviors together, making it modular, reusable, and easier to maintain.


## Four Pillars of OOP
Object-Oriented Programming (OOP) is built on four fundamental principles that ensure code is structured, reusable, and maintainable. These principles—Encapsulation, Inheritance, Polymorphism, and Abstraction—help in organizing complex systems by breaking them into manageable, modular components. They enhance security, flexibility, and scalability, making OOP a preferred approach for large-scale software development.

Key Pillars of OOP:
- Encapsulation → Hides internal details and protects data using private variables and methods.
- Inheritance → Allows new classes to reuse properties and behaviors of existing classes.
- Polymorphism → Enables different objects to use the same method but behave differently.
- Abstraction → Hides complex implementation and exposes only essential details.

# Objects

An object is a collection of key-value pairs that store related data and functions. Objects can be created using the Object constructor or object literals, which provide a simple and readable way to define objects using {}. Object literals are widely used because they make code concise, easy to read, and maintainable.

### Key Points:
- Object → A data structure that holds properties (key-value pairs) and methods.
- Object Literal → A shorthand way to define objects using { key: value }.
- Readable & Simple → Object literals make object creation concise and clear.
- No Constructor Needed → Unlike new Object(), object literals require no extra syntax.
- Easily Expandable → You can dynamically add properties and methods.

## Factory function

A factory function is a function that returns objects without using the new keyword. It provides a flexible and reusable way to create multiple instances of an object, making it useful when dealing with dynamic object creation. Factory functions help avoid redundancy and make code more scalable and maintainable.

Key Points:
- Creates Objects → Returns a new object each time it's called.
- No new Keyword → Unlike constructors, it doesn’t require new.
- Encapsulation → Keeps object creation logic inside a function.
- Reusable → Easily generate multiple objects with different values.

```js
function createCar(brand, model) {
    return {
        brand,
        model,
        drive() {
            console.log(`${this.brand} ${this.model} is driving`);
        }
    };
}

const car1 = createCar("Tesla", "Model S");
const car2 = createCar("BMW", "X5");

car1.drive(); // Tesla Model S is driving
car2.drive(); // BMW X5 is driving
```

## Constructors
A constructor function is a special function used to create and initialize objects using the new keyword. It acts as a blueprint for creating multiple objects with the same properties and methods. Constructors help in making object creation structured, reusable, and scalable.

Key Points:
- Creates Objects → Used to instantiate multiple objects from a blueprint.
- Uses new Keyword → Must be called with new to return an object.
- Capitalized Name → By convention, constructor functions start with an uppercase letter.
- Reusability → Helps avoid redundant object definitions.

## Constructor Property
The constructor property is an inbuilt property of JavaScript objects that references the function that created the object. It helps identify the constructor used to create an object and can be useful for debugging or checking object types dynamically.

Key Points:
- References the Creator Function → Points to the function that constructed the object.
- Available on All Objects → Every object inherits the constructor property.
- Useful for Type Checking → Helps determine an object’s constructor.
- Can Be Overwritten → Can be manually changed, but rarely needed.

```js
function Car(brand) {
    this.brand = brand;
}

const myCar = new Car("Tesla");

console.log(myCar.constructor); // Outputs: [Function: Car]
console.log(myCar.constructor === Car); // true
```

## Functions are Objects
In JavaScript, functions are also objects, meaning they can have properties and methods like any other object. This allows functions to store data, be assigned to variables, passed as arguments, and even have their own methods. This flexibility makes JavaScript a powerful functional programming language.

Key Points:
- Functions Have Properties → Can store data like objects.
- Can Be Assigned → Functions can be stored in variables.
- Can Be Passed Around → Used as arguments in other functions (higher-order functions).
- Can Have Methods → Functions can have their own methods and properties.
```js
function greet() {
    console.log("Hello!");
}

greet.language = "English"; // Adding a property to the function

console.log(greet.language); // Outputs: English
greet(); // Outputs: Hello!
```


## Value vs Reference Types

Data types are categorized into value types (primitives) and reference types (objects). Value types store data directly in memory, while reference types store a reference (or address) to the actual data in memory. This affects how data is copied and compared.

```Primitives are copied independently, while objects share the same reference! ```

Key Points:
- Value Types (Primitives) → Stored directly in memory.
- Reference Types (Objects) → Stored as a reference (memory address).
- Copying Behavior → Value types create independent copies, while reference types share the same memory location.
- Comparison → Value types compare actual values, while reference types compare memory addresses.

```js
// Value Type (Primitive)
let a = 10;
let b = a;  // Copying value
b = 20;
console.log(a); // 10 (unchanged)
console.log(b); // 20

// Reference Type (Object)
let obj1 = { name: "Alice" };
let obj2 = obj1;  // Copying reference
obj2.name = "Bob";
console.log(obj1.name); // Bob (changed because obj1 and obj2 reference the same object)
```

## Adding or Removing Properties
In JavaScript, objects are dynamic, meaning you can add or remove properties at any time. You can access and modify properties using dot notation (.) or bracket notation ([]). Bracket notation is useful when property names are dynamic or contain special characters.

Key Points:
- Adding Properties → Use object.property = value or object["property"] = value.
- Removing Properties → Use delete object.property.
- Bracket Notation → Needed for dynamic keys or when property names contain spaces or special characters.

```js
let person = { name: "Alice" };

// Adding properties
person.age = 25;  // Using dot notation
person["city"] = "New York";  // Using bracket notation

// Removing properties
delete person.age;

console.log(person); // { name: 'Alice', city: 'New York' }

// Using bracket notation with dynamic property name
let key = "email";
person[key] = "alice@example.com"; // Adding dynamically
console.log(person.email); // Outputs: alice@example.com
```
## Enumerating Properties
Enumerating properties means iterating over an object's keys to access its values. JavaScript provides multiple ways to do this, such as for...in loop, Object.keys(), Object.values(), and Object.entries(). These methods help when you need to process or display object properties dynamically.

Key Points:
- for...in Loop → Iterates over all enumerable properties of an object.
- Object.keys(obj) → Returns an array of property names (keys).
- Object.values(obj) → Returns an array of property values.
- Object.entries(obj) → Returns an array of key-value pairs.

```js
let person = { name: "Alice", age: 25, city: "New York" };

// Using for...in loop
for (let key in person) {
    console.log(key, person[key]); // name Alice, age 25, city New York
}

// Using Object.keys()
console.log(Object.keys(person)); // ["name", "age", "city"]

// Using Object.values()
console.log(Object.values(person)); // ["Alice", 25, "New York"]

// Using Object.entries()
console.log(Object.entries(person)); // [["name", "Alice"], ["age", 25], ["city", "New York"]]

```
## Abstraction , Private Properties and Methods
Abstraction is the concept of hiding unnecessary details and exposing only what's essential. In JavaScript, private properties and methods help achieve abstraction by restricting direct access to certain parts of an object. This improves security, maintainability, and prevents unintended modifications.

Key Points:
✔ Abstraction → Hides complex logic, exposing only what’s needed.
✔ Private Properties/Methods → Use # (private fields) or closures to keep data hidden.
✔ Encapsulation → Prevents direct modification of internal object states.
✔ Better Security → Protects sensitive data from external changes.

```js
class Car {
    #engineStatus = "off"; // Private property

    start() {
        this.#toggleEngine(true);
        console.log("Car started");
    }

    #toggleEngine(status) { // Private method
        this.#engineStatus = status ? "on" : "off";
    }
}

const myCar = new Car();
myCar.start(); // Car started
console.log(myCar.#engineStatus); // ❌ Error: Private field not accessible
```
## Getters and Setters
Getters and setters allow controlled access to object properties. A getter (get) retrieves a property value, while a setter (set) modifies it. They help encapsulate logic, validate data, and restrict direct property modification, making objects more secure and maintainable.

Key Points:
✔ Getter (get) → Allows reading a property like a variable.
✔ Setter (set) → Controls modification of a property with validation.
✔ Encapsulation → Hides direct property access and enforces rules.
✔ Improves Security → Prevents invalid data from being set.
```js
class Person {
    constructor(name) {
        this._name = name; // Convention: Use _ for internal properties
    }

    get name() {
        return this._name.toUpperCase(); // Custom logic while getting
    }

    set name(newName) {
        if (newName.length > 2) {
            this._name = newName; // Custom validation
        } else {
            console.log("Name must be at least 3 characters long");
        }
    }
}

const person = new Person("Alice");
console.log(person.name); // ALICE (Getter in action)

person.name = "Bo"; // ❌ Invalid (Setter validation)
person.name = "Bob"; // ✅ Valid update
console.log(person.name); // BOB
```

# Prototypes
Prototypes allow objects to inherit properties and methods from other objects. Every object in JavaScript has an internal link (__proto__) to its prototype, enabling reuse of functions and efficient memory usage. This forms the basis of prototypal inheritance.

``` 
Think prototype as parent
```

Key Points:
- Prototype Chain → Objects inherit properties/methods from their prototype.
- Memory Efficient → Shared methods are stored in one place, not copied.
- Custom Methods → You can add methods to an object’s prototype.
- Prototypal Inheritance → Objects inherit behavior from other objects.

```js
function Person(name) {
    this.name = name;
}

// Adding a method to the prototype
Person.prototype.greet = function () {
    console.log(`Hello, my name is ${this.name}`);
};

const person1 = new Person("Alice");
const person2 = new Person("Bob");

person1.greet(); // Hello, my name is Alice
person2.greet(); // Hello, my name is Bob

console.log(person1.__proto__ === Person.prototype); // true
```

## Inheritance
Inheritance allows one object to inherit properties and methods from another, enabling code reuse and modular design. In JavaScript, inheritance is achieved using prototypes or the class keyword (extends). This makes it easier to create specialized objects based on existing ones.

Key Points:
- Prototypal Inheritance → Objects inherit from other objects via prototypes.
- Class-Based Inheritance → Uses class and extends to create child classes.
- Code Reusability → Avoids duplicate code by reusing parent functionality.
- Super Keyword → Calls methods from the parent class inside a child class.
```js
class Animal {
    constructor(name) {
        this.name = name;
    }
    makeSound() {
        console.log(`${this.name} makes a sound`);
    }
}

class Dog extends Animal {
    bark() {
        console.log(`${this.name} barks! 🐶`);
    }
}

const dog = new Dog("Buddy");
dog.makeSound(); // Buddy makes a sound
dog.bark(); // Buddy barks! 🐶
```

## Prototypes and Prototypical Inheritance
Prototypes allow objects to inherit properties and methods from other objects. Prototypical inheritance enables JavaScript objects to inherit from other objects directly, forming a prototype chain. This is more flexible than classical inheritance, as objects can dynamically inherit behavior without needing classes.

Key Points:
- Prototype Chain → Objects inherit from their prototype (__proto__).
- Shared Methods → Methods defined in a prototype are shared across instances.
- Efficient Memory Usage → Prevents duplication of functions in each object.
- Dynamic Inheritance → Objects can inherit behavior at runtime.

```js
function Animal(name) {
    this.name = name;
}

// Adding method to prototype
Animal.prototype.makeSound = function () {
    console.log(`${this.name} makes a sound`);
};

function Dog(name, breed) {
    Animal.call(this, name); // Inheriting properties
    this.breed = breed;
}

// Inheriting methods
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

Dog.prototype.bark = function () {
    console.log(`${this.name} barks! 🐶`);
};

const dog = new Dog("Buddy", "Labrador");
dog.makeSound(); // Buddy makes a sound
dog.bark(); // Buddy barks! 🐶

console.log(dog.__proto__ === Dog.prototype); // true
console.log(Dog.prototype.__proto__ === Animal.prototype); // true
```

## Multilevel Inheritance

Multilevel inheritance occurs when a class (or object) inherits from another class, which itself inherits from another. This creates a chain of inheritance, where properties and methods are passed down through multiple levels, promoting code reusability and modularity.

Key Points:
- Chained Inheritance → A child class inherits from a parent, which itself inherits from another class.
- Code Reusability → Avoids redundant code by passing down methods and properties.
- Prototype Chain → Each level in the hierarchy links to the previous one.
- Super Keyword → Used to call parent class methods in a subclass.

```js
class Animal {
    constructor(name) {
        this.name = name;
    }
    makeSound() {
        console.log(`${this.name} makes a sound`);
    }
}

class Mammal extends Animal {
    feedMilk() {
        console.log(`${this.name} feeds milk`);
    }
}

class Dog extends Mammal {
    bark() {
        console.log(`${this.name} barks! 🐶`);
    }
}

const dog = new Dog("Buddy");
dog.makeSound(); // Buddy makes a sound
dog.feedMilk(); // Buddy feeds milk
dog.bark(); // Buddy barks! 🐶

```
## Property Descriptors

Property descriptors define the behavior of object properties in JavaScript. Every property has a descriptor that controls whether the property is writable, enumerable, and configurable. Using Object.defineProperty(), you can customize or lock down how properties behave, adding more control over your objects.

Key Points:
- Writable → Can the property's value be changed?
- Enumerable → Will the property show up in loops like for...in?
- Configurable → Can the property be deleted or modified?
- Control Access → Fine-tune object property behavior.

```js
let person = {};

Object.defineProperty(person, "name", {
    value: "Alice",
    writable: false, // Can't change value
    enumerable: true, // Will show in loops
    configurable: false // Can't delete or redefine
});

console.log(person.name); // Alice
person.name = "Bob"; // ❌ Won't change because writable: false
console.log(person.name); // Alice

for (let key in person) {
    console.log(key); // name (because enumerable: true)
}

delete person.name; // ❌ Won't delete because configurable: false
console.log(person.name); // Alice
```

## Constructor Prototypes
when you create an object using a constructor function, methods or properties shared across all instances are added to the constructor’s prototype. This allows all instances to access the same method without duplicating it in each object, making memory usage efficient and enabling prototypal inheritance.

Key Points:
- Constructor Function → Creates multiple similar objects.
- Prototype Property → Attach shared methods to save memory.
- Inheritance → All instances inherit methods from the prototype.
- Efficient → One method stored, shared by all instances.

```js
function Person(name) {
    this.name = name;
}

// Adding method to constructor's prototype
Person.prototype.greet = function () {
    console.log(`Hello, I am ${this.name}`);
};

const person1 = new Person("Alice");
const person2 = new Person("Bob");

person1.greet(); // Hello, I am Alice
person2.greet(); // Hello, I am Bob

console.log(person1.__proto__ === Person.prototype); // true
```

## Prototype vs Instance Members
Instance members are properties or methods defined inside the constructor function; each object instance gets its own copy. Prototype members, on the other hand, are defined on the constructor’s prototype and are shared across all instances, saving memory and enabling inheritance.

Key Points:
- Instance Members → Defined inside constructor, unique to each object.
- Prototype Members → Defined on prototype, shared by all instances.
- Memory Efficient → Prototype members avoid duplication.
- Customization → Use instance members for unique data, prototype members for common behavior.

```js
function Person(name) {
    // Instance member
    this.name = name;
    this.sayHello = function () {
        console.log(`Hi, I am ${this.name}`);
    };
}

// Prototype member
Person.prototype.greet = function () {
    console.log(`Hello from ${this.name}`);
};

const person1 = new Person("Alice");
const person2 = new Person("Bob");

// Instance method (each has own copy)
person1.sayHello(); // Hi, I am Alice
person2.sayHello(); // Hi, I am Bob

// Prototype method (shared)
person1.greet(); // Hello from Alice
person2.greet(); // Hello from Bob

console.log(person1.sayHello === person2.sayHello); // false (separate copies)
console.log(person1.greet === person2.greet); // true (shared)
```

## Iterating Instance and Prototype Members
you can iterate over both instance and prototype members using loops like for...in. However, instance members are directly present in the object, while prototype members are inherited via the prototype chain. To distinguish between them, you can use the hasOwnProperty() method, which checks if a property belongs directly to the instance.

Key Points:
- for...in Loop → Iterates over both instance and prototype members.
- hasOwnProperty() → Filters out prototype members, returning only instance members.
- Prototype Chain → Prototype members appear unless filtered.
- Control → Helps differentiate between own and inherited properties.

##  Avoid Extending the Built-in Objects
Extending built-in objects like Array, Object, or String might seem convenient, but it's discouraged. Modifying or adding methods to their prototypes can lead to unexpected behavior, conflicts with other libraries, and can break future updates, making your code less predictable and harder to maintain.

Key Points:
- Risk of Conflicts → Other libraries or future JavaScript versions might use the same method name.
- Unexpected Behavior → Can cause bugs when looping or using built-in functions.
- Hard to Maintain → Makes debugging and upgrading difficult.
- Best Practice → Create utility/helper functions instead of modifying built-ins.

```js
// Bad practice: Extending built-in prototype
Array.prototype.sayHello = function () {
    console.log("Hello from Array!");
};

const arr = [1, 2, 3];
arr.sayHello(); // Works, but risky!

for (let item in arr) {
    console.log(item); // Will also include 'sayHello' - unexpected behavior!
}
```

# Prototypical Inheritance 
Prototypical inheritance allows one object to inherit properties and methods from another object through its prototype. Instead of classes, JavaScript uses a prototype chain where objects link to other objects, enabling flexible and dynamic inheritance. This promotes code reuse and shared behavior without duplicating functionality.

Key Points:
- Prototype Chain → Objects inherit from other objects' prototypes.
- Shared Methods → Reduces memory usage, as methods are not copied to each instance.
- Dynamic Inheritance → Objects can inherit behavior at runtime.
- Flexible Structure → No rigid class hierarchy needed.

```js
const animal = {
    eat: function () {
        console.log(`${this.name} is eating`);
    }
};

const dog = {
    name: "Buddy"
};

// Setting prototype
Object.setPrototypeOf(dog, animal);

dog.eat(); // Buddy is eating
console.log(dog.__proto__ === animal); // true
```

## Creating Your Own Prototypical Inheritance
You can create your own prototypical inheritance by manually linking objects using Object.create() or by setting the prototype of one constructor function to an instance of another. This allows child objects to inherit properties and methods from parent objects, enabling code reuse and hierarchical relationships.

Key Points:
- Object.create() → Directly sets the prototype of a new object.
- Constructor Inheritance → Child constructor’s prototype points to parent’s prototype.
- Shared Behavior → Child objects can access parent methods.
- Flexible & Dynamic → Easy to modify or extend inheritance chains.

```js
const animal = {
    eat: function () {
        console.log(`${this.name} is eating`);
    }
};

const dog = Object.create(animal);
dog.name = "Max";
dog.eat(); // Max is eating
```

```js
function Animal(name) {
    this.name = name;
}
Animal.prototype.eat = function () {
    console.log(`${this.name} eats`);
};

function Dog(name) {
    Animal.call(this, name); // Call parent constructor
}
Dog.prototype = Object.create(Animal.prototype); // Inherit prototype
Dog.prototype.constructor = Dog;

const dog1 = new Dog("Buddy");
dog1.eat(); // Buddy eats
```
## Resetting the Constructor
When setting up prototypical inheritance using Object.create(), the child’s prototype inherits from the parent, but the constructor property of the child points to the parent constructor by default. To maintain clarity and avoid confusion, it’s important to reset the constructor property back to the child’s constructor.

Key Points:
- Prototype Chain Issue → Child's prototype constructor points to parent constructor.
- Why Reset? → Keeps the correct reference to child’s constructor.
- Maintains Clarity → Helps in debugging and object identification.
- Simple Fix → Use Child.prototype.constructor = Child;

```js
function Animal(name) {
    this.name = name;
}
Animal.prototype.eat = function () {
    console.log(`${this.name} eats`);
};

function Dog(name) {
    Animal.call(this, name);
}

// Inherit from Animal
Dog.prototype = Object.create(Animal.prototype);

// Resetting constructor
Dog.prototype.constructor = Dog;

const dog1 = new Dog("Buddy");
console.log(dog1.constructor === Dog); // true
console.log(dog1.constructor); // Outputs: Dog function
```

## Calling the Super Constructor
when creating inheritance using constructor functions, the child constructor needs to call the parent (super) constructor to properly initialize the inherited properties. This is done using Parent.call(this, ...) inside the child constructor. It ensures that the parent’s initialization logic runs for each child instance.

Key Points:
- Parent Initialization → Use Parent.call(this, ...) to inherit properties.
- Avoid Duplication → Ensures parent setup runs in child.
- Proper Context → this refers to the child instance during the call.
- Required for Inherited Properties → Without it, child lacks parent properties.

```js
function Animal(name) {
    this.name = name;
}

function Dog(name, breed) {
    Animal.call(this, name); // Call super constructor
    this.breed = breed;
}

const dog1 = new Dog("Buddy", "Labrador");
console.log(dog1.name);  // Buddy
console.log(dog1.breed); // Labrador
```

## Intermediate Function Inheritance

Intermediate function inheritance is a technique used to set up inheritance between two constructor functions without directly modifying the prototype chain, helping to avoid unwanted side effects. It introduces a temporary constructor function as a bridge to correctly link the prototypes while keeping the child constructor’s prototype clean and safe.

Key Points:
- Temporary Constructor Function → Acts as a middle layer.
- Avoids Direct Modification → Prevents altering parent prototypes directly.
- Safe & Clean Inheritance → Keeps prototype chains intact.
- Maintains Constructor Reference → Child constructor remains correct.

```js
function Animal(name) {
    this.name = name;
}
Animal.prototype.eat = function () {
    console.log(`${this.name} eats`);
};

function Dog(name) {
    Animal.call(this, name);
}

// Intermediate function
function Temp() {}
Temp.prototype = Animal.prototype;

// Set up inheritance
Dog.prototype = new Temp();
Dog.prototype.constructor = Dog;

const dog1 = new Dog("Buddy");
dog1.eat(); // Buddy eats
console.log(dog1.constructor === Dog); // true
```


## Method Overriding

Method overriding occurs when a child object or subclass redefines a method inherited from its parent, providing a more specific or customized implementation. It’s a powerful way to extend or modify behavior while keeping the base functionality available if needed.

Key Points:
- Same Method Name → Child provides its own version of the method.
- Custom Behavior → Allows tailoring inherited methods.
- Can Still Call Parent Method → Use Parent.prototype.method.call(this) if needed.
- Polymorphism → Enables flexible and dynamic behavior changes.

```js
function Animal(name) {
    this.name = name;
}
Animal.prototype.speak = function () {
    console.log(`${this.name} makes a sound`);
};

function Dog(name) {
    Animal.call(this, name);
}
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

// Overriding speak method
Dog.prototype.speak = function () {
    console.log(`${this.name} barks`);
};

const dog1 = new Dog("Buddy");
dog1.speak(); // Buddy barks
```

## Polymorphism

Polymorphism means "many forms" — it allows different objects to be treated as if they are instances of the same parent, yet each can perform behavior differently. It’s achieved by having different classes or objects implement the same method name but with different functionality, allowing flexible and dynamic code without worrying about exact object types.

Key Points:
- Same Interface, Different Behavior → Different objects share method names but behave differently.
- Method Overriding Enables It → Each subclass provides its own implementation.
- Simplifies Code → Write general code without worrying about specific object types.
- Supports Extensibility → Easily add new object types without changing existing code.

```js
function Animal(name) {
    this.name = name;
}
Animal.prototype.speak = function () {
    console.log(`${this.name} makes a sound`);
};

function Dog(name) {
    Animal.call(this, name);
}
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;
Dog.prototype.speak = function () {
    console.log(`${this.name} barks`);
};

function Cat(name) {
    Animal.call(this, name);
}
Cat.prototype = Object.create(Animal.prototype);
Cat.prototype.constructor = Cat;
Cat.prototype.speak = function () {
    console.log(`${this.name} meows`);
};

// Polymorphism in action
const animals = [new Dog("Buddy"), new Cat("Kitty")];

animals.forEach(animal => animal.speak());
// Output:
// Buddy barks
// Kitty meows
```

## When to Use Inheritance
Inheritance is best used when multiple objects share common properties or behavior, and you want to avoid code duplication by moving shared logic to a parent object or class. It helps create a clear hierarchical relationship, making the code organized, reusable, and easier to maintain.

Key Points:
- Shared Behavior → When multiple objects need the same methods or properties.
- Avoid Duplication → Move common logic to a parent object.
- Logical Hierarchies → Use when there’s a natural “is-a” relationship (e.g., Dog is an Animal).
- Code Maintenance → Changes in the parent reflect across all child objects.
- Extensibility → Easily add new child types without rewriting common code.

```js
function Animal(name) {
    this.name = name;
}
Animal.prototype.eat = function () {
    console.log(`${this.name} eats`);
};

function Dog(name) {
    Animal.call(this, name);
}
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

const dog1 = new Dog("Buddy");
dog1.eat(); // Buddy eats
```


## Mixins
Mixins are a way to reuse reusable chunks of functionality across multiple unrelated objects without using inheritance. Instead of forming a parent-child relationship, mixins allow you to copy methods or properties into any object or class, providing flexibility and avoiding rigid hierarchies. It’s great when you want multiple behaviors in different objects that don't fit into a single inheritance chain.

Key Points:
- No Hierarchy Needed → Use when inheritance doesn't make sense.
- Behavior Sharing → Share methods/properties across different objects.
- Flexible & Modular → Easily compose behaviors without tight coupling.
- Avoids Deep Inheritance Chains → Keeps code simple and flat.
- Implemented via Object.assign() or functions.

```js
let canEat = {
    eat: function() {
        console.log("Eating...");
    }
};

let canWalk = {
    walk: function() {
        console.log("Walking...");
    }
};

function Person(name) {
    this.name = name;
}

// Apply mixins
Object.assign(Person.prototype, canEat, canWalk);

const person1 = new Person("John");
person1.eat();  // Eating...
person1.walk(); // Walking...
```
# ES6 Classes 

- ES6 Classes
- Hoisting
- Static Methods
- The This Keyword
- Private Members Using Symbols
- Private Members Using WeakMaps
- Getters and Setters
- Inheritance
- Method Overriding