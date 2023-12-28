# TypeScript Advanced Types: Union Types

Union types in TypeScript allow you to express a value that can be one of several types. They provide flexibility and are often used to represent scenarios where a value can have different, but known, types. Here's an introduction to using union types in TypeScript.

## Basics of Union Types

To define a union type, use the `|` (pipe) symbol between the types:

```typescript
let myVariable: number | string;

myVariable = 42;        // Valid assignment
myVariable = "Hello";   // Valid assignment
// myVariable = true;   // Error: Type 'boolean' is not assignable to type 'number | string'.
```

In this example, `myVariable` can be either a `number` or a `string`, but not any other type.

## Type Guards with Unions

When working with union types, you may want to perform different actions based on the actual type of a variable. Type guards help you narrow down the type within a specific code block:

```typescript
function printLength(value: number | string): void {
  if (typeof value === 'number') {
    console.log(`Length of the number: ${value.toString().length}`);
  } else {
    console.log(`Length of the string: ${value.length}`);
  }
}

printLength(42);          // Output: Length of the number: 2
printLength("Hello");     // Output: Length of the string: 5
```

Here, the `typeof` operator serves as a type guard for the `number` type.

## Handling Null or Undefined with Unions

Union types are often used to handle scenarios involving `null` or `undefined`:

```typescript
let nullableValue: string | null;

nullableValue = "Hello";  // Valid assignment
nullableValue = null;     // Valid assignment
// nullableValue = 42;    // Error: Type 'number' is not assignable to type 'string | null'.

if (nullableValue !== null) {
  console.log(`Length of the string: ${nullableValue.length}`);
} else {
  console.log(`Value is null`);
}
```

In this example, `nullableValue` can be either a `string` or `null`.

## Combining Union Types with Literal Types

You can combine union types with literal types to create specific sets of allowed values:

```typescript
type Direction = "left" | "right" | "up" | "down";

function move(direction: Direction): void {
  console.log(`Moving ${direction}`);
}

move("left");   // Valid call
move("up");     // Valid call
// move("diagonal"); // Error: Argument of type '"diagonal"' is not assignable to parameter of type 'Direction'.
```

Here, `Direction` is a union type with literal values, allowing only specific directions.

Union types are a powerful tool for handling a wide range of scenarios where a value can have multiple possible types. They enhance type safety and expressiveness in TypeScript.

