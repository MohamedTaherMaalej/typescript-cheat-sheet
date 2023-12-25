# TypeScript Generics: Generic Functions

Generic functions in TypeScript allow you to create functions that can work with different types while maintaining type safety. The use of generic type parameters enables you to write functions that are flexible and reusable. Here's how you can use and work with generic functions in TypeScript.

## Basic Generic Function

To create a generic function, use a type parameter (often denoted by a single uppercase letter) within angle brackets `<>`:

```typescript
function identity<T>(arg: T): T {
  return arg;
}

let result: number = identity<number>(42);
let value: string = identity<string>("Hello, Generics!");
```

In this example, `identity` is a generic function that takes a value of type `T` and returns a value of the same type. The type parameter `T` is specified when calling the function.

## Array Map with Generics

A common use case for generic functions is with array operations like `map`. Here's a generic version of the `map` function:

```typescript
function mapArray<T, U>(array: T[], mapper: (value: T) => U): U[] {
  return array.map(mapper);
}

let numbers: number[] = [1, 2, 3, 4, 5];
let squaredNumbers: number[] = mapArray(numbers, (n) => n * n);

let words: string[] = ["apple", "banana", "cherry"];
let wordLengths: number[] = mapArray(words, (word) => word.length);
```

In this example, `mapArray` is a generic function that takes an array of type `T` and a mapping function. It returns an array of type `U` based on the applied mapping function.

## Generic Constraints

You can apply constraints to generic types using the `extends` keyword to ensure that certain properties or methods are available on the generic type:

```typescript
interface HasLength {
  length: number;
}

function getLength<T extends HasLength>(value: T): number {
  return value.length;
}

let strLength: number = getLength("Hello");
let arrLength: number = getLength([1, 2, 3]);
```

Here, the `getLength` function works with any type that has a `length` property.

## Using Multiple Type Parameters

You can use multiple type parameters in a generic function to capture relationships between types:

```typescript
function pair<T, U>(first: T, second: U): [T, U] {
  return [first, second];
}

let numberStringPair: [number, string] = pair(42, "forty-two");
```

In this example, the `pair` function takes two values of different types and returns a tuple of those types.

Generic functions provide a powerful tool for writing flexible and reusable code in TypeScript. They are widely used in various scenarios to enhance type safety and code expressiveness.
