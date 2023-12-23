# TypeScript Classes: Inheritance

In TypeScript, classes support inheritance, allowing you to create a hierarchy of classes where a subclass can inherit properties and methods from a base class. Here's how you can use and work with inheritance in TypeScript.

## Creating a Base Class

To create a base class, define a class with properties and methods that you want to share with subclasses:

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

In the above example, `Animal` is the base class.

## Creating a Subclass

To create a subclass that inherits from the base class, use the `extends` keyword:

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

  // Additional method in the subclass
  fetch(): void {
    console.log("Fetching the ball!");
  }
}
```

In this example, `Dog` is a subclass of `Animal` and inherits its properties and methods. The `super` keyword is used to call the constructor of the base class.

## Creating Instances of Subclass

You can create instances of the subclass and use both inherited and subclass-specific methods and properties:

```typescript
let myDog = new Dog("Buddy", 2, "Golden Retriever");

console.log(myDog.name);       // Output: Buddy
console.log(myDog.age);        // Output: 2
myDog.makeSound();             // Output: Woof! Woof!
myDog.fetch();                 // Output: Fetching the ball!
```

## Access Modifiers in Inheritance

You can use access modifiers (`public`, `private`, `protected`) to control the visibility of properties and methods in both the base class and the subclass:

```typescript
class Animal {
  protected sound: string;

  constructor(sound: string) {
    this.sound = sound;
  }

  makeSound(): void {
    console.log(this.sound);
  }
}

class Dog extends Animal {
  // Accessing the protected property from the base class
  bark(): void {
    console.log(this.sound);
  }
}
```

In this example, the `sound` property is `protected` in the base class, allowing the subclass `Dog` to access it.

These are basic examples of working with inheritance in TypeScript. Explore more advanced features and use cases in the TypeScript documentation as needed.

