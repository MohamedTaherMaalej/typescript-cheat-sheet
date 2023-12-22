# TypeScript Classes: Basics

In TypeScript, classes provide a way to create objects with properties and methods. They allow you to model real-world entities with a clear structure and encapsulation. Here's how you can use and work with classes in TypeScript.

## Declaring Classes

To declare a class, use the `class` keyword:

```typescript
class Animal {
  // Properties
  name: string;
  age: number;

  // Constructor
  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  // Method
  makeSound(): void {
    console.log("Some generic sound");
  }
}
```

In the above example, the `Animal` class has properties (`name` and `age`), a constructor, and a method (`makeSound`).

## Creating Instances

To create an instance of a class, use the `new` keyword followed by the class name:

```typescript
let myPet = new Animal("Fluffy", 3);
```

This creates a new `Animal` object with the specified name and age.

## Accessing Properties and Methods

You can access properties and methods using the dot notation:

```typescript
console.log(myPet.name);      // Output: Fluffy
console.log(myPet.age);       // Output: 3
myPet.makeSound();            // Output: Some generic sound
```

## Inheritance

Classes in TypeScript support inheritance. You can create a subclass that extends a base class:

```typescript
class Dog extends Animal {
  // Additional properties
  breed: string;

  // Additional constructor logic
  constructor(name: string, age: number, breed: string) {
    super(name, age); // Call the base class constructor
    this.breed = breed;
  }

  // Override the makeSound method
  makeSound(): void {
    console.log("Woof! Woof!");
  }
}
```

In this example, the `Dog` class extends the `Animal` class, inheriting its properties and methods.

## Access Modifiers

You can use access modifiers (`public`, `private`, `protected`) to control the visibility of properties and methods:

```typescript
class MyClass {
  private secretNumber: number;

  constructor() {
    this.secretNumber = 42;
  }

  getSecretNumber(): number {
    return this.secretNumber;
  }
}
```

Here, `secretNumber` is private and can only be accessed within the `MyClass`.

These are basic examples of working with classes in TypeScript. Explore more advanced features and use cases in the TypeScript documentation as needed.

