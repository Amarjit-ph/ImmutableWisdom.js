# Ultimate Javascript

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
- 13- Cheat Sheet
- 14- Exercise- Stopwatch
- 15- Solution- Stopwatch


Prototypes 

- 1- Inheritance
- 2- Prototypes and Prototypical Inheritance
- 3- Multilevel Inheritance
- 4- Property Descriptors
- 5- Constructor Prototypes
- 6- Prototype vs Instance Members
- 7- Iterating Instance and Prototype Members
- 8- Avoid Extending the Built-in Objects
- 9- Cheat Sheet
- 10- Exercise
- 11- Solution


Prototypical Inheritance 
- 1- Creating Your Own Prototypical Inheritance
- 2- Resetting the Constructor
- 3- Calling the Super Constructor
- 4- Intermediate Function Inheritance
- 5- Method Overriding
- 6- Polymorphism
- 7- When to Use Inheritance
- 8- Mixins
- 9- Cheat Sheet
- 10- Exercise- Prototypical Inheritance
- 11- Solution- Prototypical Inheritance
- 12- Exercise- Polymorphism
- 13- Solution- Polymorphism

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
- 10- Cheat Sheet
- 11- Exercise
- 12- Solution


ES6 Tooling 
- 1- Modules
- 2- CommonJS Modules
- 3- ES6 Modules
- 4- ES6 Tooling
- 5- Babel
- 6- Webpack
- 7- Cheat Sheet
- 8- What to Learn Next




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