# TypeScript Generics: Introduction

Generics in TypeScript allow you to create flexible and reusable components by enabling the definition of functions and classes with placeholders for the types they use. This enables you to write code that is type-safe while maintaining flexibility. Here's an introduction to generics in TypeScript.

## What are Generics?

Generics provide a way to create functions and classes that work with a variety of data types while maintaining type safety. Instead of specifying a concrete type, you can use a placeholder, typically represented by the letter 'T', to denote a generic type.

```typescript
function identity<T>(arg: T): T {
  return arg;
}

let result: number = identity<number>(42);
let value: string = identity<string>("Hello, Generics!");
```

In this example, the `identity` function is generic and can be used with different types (`number` and `string` in this case).

## Using Generics with Arrays

Generics are often used with arrays to create reusable functions:

```typescript
function reverseArray<T>(array: T[]): T[] {
  return array.reverse();
}

let numbers: number[] = [1, 2, 3, 4, 5];
let reversedNumbers: number[] = reverseArray(numbers);

let words: string[] = ["apple", "banana", "cherry"];
let reversedWords: string[] = reverseArray(words);
```

Here, `reverseArray` is a generic function that can reverse arrays of different types.

## Creating Generic Classes

You can also create generic classes to achieve flexibility:

```typescript
class Box<T> {
  private content: T;

  constructor(value: T) {
    this.content = value;
  }

  getContent(): T {
    return this.content;
  }
}

let numberBox = new Box<number>(42);
let stringBox = new Box<string>("Hello, Generics!");

console.log(numberBox.getContent()); // Output: 42
console.log(stringBox.getContent()); // Output: Hello, Generics!
```

In this example, the `Box` class is generic and can hold values of different types.

Generics provide a powerful way to create reusable and type-safe code in TypeScript. They are widely used in libraries and frameworks to build flexible and robust components.

