# TypeScript Interfaces: Function Types

In TypeScript, interfaces can represent not only the shape of objects but also the structure of functions. Function types in interfaces define the signature of a function, including parameter types and return type. Here's how you can use and work with function types in TypeScript interfaces.

## Declaring Function Types in Interfaces

To declare a function type within an interface, specify the parameters and return type as if you were defining a function:

```typescript
interface MathOperation {
  (x: number, y: number): number;
}
```

In the above example, the `MathOperation` interface represents a function that takes two parameters of type `number` and returns a value of type `number`.

## Implementing Function Types

When implementing a function type interface, the function must adhere to the specified parameter types and return type:

```typescript
let add: MathOperation = function(x, y) {
  return x + y;
};

let multiply: MathOperation = function(x, y) {
  return x * y;
};
```

Both `add` and `multiply` functions conform to the `MathOperation` interface.

## Function Type as a Property

You can also use function types as properties in interfaces:

```typescript
interface Calculator {
  add: MathOperation;
  subtract: MathOperation;
}
```

In this example, the `Calculator` interface defines two properties, `add` and `subtract`, both of which are of the `MathOperation` function type.

## Callback Functions

Function types are commonly used to define callback functions:

```typescript
interface AsyncCallback {
  (data: string): void;
}
```

The `AsyncCallback` interface represents a function that takes a `string` parameter and returns `void`. This can be used as a callback function signature.

## Function Types in Class Interfaces

Function types can be part of class interfaces, defining methods:

```typescript
interface Printer {
  print: (content: string) => void;
}

class ConsolePrinter implements Printer {
  print(content: string) {
    console.log(content);
  }
}
```

In this example, the `ConsolePrinter` class implements the `Printer` interface with a `print` method.

These are basic examples of working with function types in TypeScript interfaces. Explore more advanced features and use cases in the TypeScript documentation as needed.

