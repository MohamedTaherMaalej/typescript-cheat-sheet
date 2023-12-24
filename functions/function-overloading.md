# TypeScript Functions: Function Overloading

Function overloading in TypeScript allows you to define multiple function signatures for the same function name. This enables the compiler to understand and enforce different use cases of a function. Here's how you can use and work with function overloading in TypeScript.

## Basic Function Overloading

To overload a function, provide multiple function signatures in the same order they should be checked by the compiler:

```typescript
function greet(name: string): string;
function greet(firstName: string, lastName: string): string;

function greet(arg1: string, arg2?: string): string {
  if (arg2) {
    return `Hello, ${arg1} ${arg2}!`;
  } else {
    return `Hello, ${arg1}!`;
  }
}
```

In this example, the `greet` function is overloaded with two signatures. It can take either a single `name` parameter or `firstName` and `lastName` parameters.

## Overloading with Union Types

You can use union types in function parameters to represent multiple possible types:

```typescript
function printID(id: string | number): void {
  console.log(`ID: ${id}`);
}
```

Here, `printID` can take either a `string` or a `number` as its parameter.

## Overloading with Function Types

You can also use function types in overloads to represent callbacks with different parameter lists:

```typescript
type EventHandler = (event: MouseEvent) => void;

function on(element: HTMLElement, event: string, handler: EventHandler): void;
function on(element: HTMLElement, event: string, selector: string, handler: EventHandler): void;

function on(element: HTMLElement, event: string, arg1: string | EventHandler, arg2?: EventHandler): void {
  // Implementation
}
```

In this example, the `on` function is overloaded to handle both direct event handlers and delegated event handlers with a selector.

## Discriminated Unions for Function Overloads

You can use discriminated unions to create more complex overloads with shared properties:

```typescript
type Shape = { kind: "circle"; radius: number } | { kind: "rectangle"; width: number; height: number };

function calculateArea(shape: Shape): number {
  switch (shape.kind) {
    case "circle":
      return Math.PI * shape.radius ** 2;
    case "rectangle":
      return shape.width * shape.height;
  }
}
```

Here, `calculateArea` is overloaded based on the discriminated union `kind` property.

These are basic examples of working with function overloading in TypeScript. Explore more advanced features and use cases in the TypeScript documentation as needed.

