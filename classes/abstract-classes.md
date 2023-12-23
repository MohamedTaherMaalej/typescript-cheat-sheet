# TypeScript Classes: Abstract Classes

In TypeScript, an abstract class is a class that cannot be instantiated directly. It is meant to serve as a base class for other classes and can contain abstract methods, which must be implemented by derived classes. Here's how you can use and work with abstract classes in TypeScript.

## Declaring Abstract Classes

To declare an abstract class, use the `abstract` keyword:

```typescript
abstract class Shape {
  // Abstract property (can also be methods)
  abstract area: number;

  // Regular method
  displayArea(): void {
    console.log(`Area: ${this.area}`);
  }

  // Abstract method
  abstract calculateArea(): void;
}
```

In the above example, the `Shape` class is declared as abstract, and it contains an abstract property (`area`) and an abstract method (`calculateArea`).

## Extending Abstract Classes

Abstract classes can be extended by other classes. The derived class must implement all abstract properties and methods:

```typescript
class Circle extends Shape {
  // Implementing the abstract property
  area: number;

  // Implementing the abstract method
  calculateArea(): void {
    this.area = Math.PI * Math.pow(5, 2);
  }
}

let circle = new Circle();
circle.calculateArea();
circle.displayArea(); // Output: Area: 78.53981633974483
```

In this example, the `Circle` class extends the abstract `Shape` class and implements the abstract property and method.

## Abstract Methods

Abstract methods are declared in abstract classes but do not have an implementation in the base class. They must be implemented by derived classes:

```typescript
abstract class Printer {
  abstract print(content: string): void;
}

class ConsolePrinter extends Printer {
  print(content: string): void {
    console.log(content);
  }
}

let printer = new ConsolePrinter();
printer.print("Hello, TypeScript!"); // Output: Hello, TypeScript!
```

In this example, the `Printer` abstract class declares an abstract method `print`, and the `ConsolePrinter` class implements it.

## Abstract Constructors

Abstract classes can also have abstract constructors. Subclasses must provide their own constructor implementations:

```typescript
abstract class Vehicle {
  abstract wheels: number;

  constructor(protected color: string) {}

  abstract start(): void;
}

class Car extends Vehicle {
  wheels: number = 4;

  start(): void {
    console.log(`The car is starting. Color: ${this.color}`);
  }
}

let myCar = new Car("Blue");
myCar.start(); // Output: The car is starting. Color: Blue
```

Here, the `Vehicle` abstract class has an abstract property (`wheels`), an abstract method (`start`), and a parameterized abstract constructor.

These are basic examples of working with abstract classes in TypeScript. Explore more advanced features and use cases in the TypeScript documentation as needed.


