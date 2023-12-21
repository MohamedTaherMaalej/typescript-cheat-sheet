# TypeScript Interfaces: Basics

In TypeScript, an interface is a way to define a contract for the shape of an object. It specifies the properties and methods that an object must have to be considered of that type. Here's how you can use and work with interfaces in TypeScript.

## Declaring Interfaces

You declare an interface using the `interface` keyword:

```typescript
interface Person {
  firstName: string;
  lastName: string;
  age: number;
}
```

In the above example, the `Person` interface defines the structure of an object with `firstName`, `lastName`, and `age` properties.

## Implementing Interfaces

You can use interfaces to enforce a specific structure for objects:

```typescript
let person: Person = {
  firstName: "John",
  lastName: "Doe",
  age: 30
};
```

In this case, `person` must adhere to the structure defined by the `Person` interface.

## Optional Properties

You can make properties optional in an interface by using the `?` symbol:

```typescript
interface Car {
  make: string;
  model: string;
  year?: number; // Optional property
}
```

Objects that implement the `Car` interface may or may not have the `year` property.

## Readonly Properties

You can mark properties as `readonly`, meaning they can only be assigned a value when the object is created:

```typescript
interface Point {
  readonly x: number;
  readonly y: number;
}
```

Once a `Point` object is created, its `x` and `y` properties cannot be modified.

## Function Types in Interfaces

Interfaces can also define function types:

```typescript
interface Greeter {
  (name: string): string;
}
```

This `Greeter` interface represents a function that takes a `name` parameter and returns a string.

## Extending Interfaces

You can extend an interface using the `extends` keyword:

```typescript
interface Employee extends Person {
  employeeId: number;
}
```

The `Employee` interface inherits the properties from the `Person` interface and adds an `employeeId` property.

These are basic examples of working with interfaces in TypeScript. Explore more advanced features and use cases in the TypeScript documentation as needed.
