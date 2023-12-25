# TypeScript Generics: Generic Classes

Generic classes in TypeScript allow you to create classes that work with multiple data types while maintaining type safety. They enable you to write reusable and flexible components that can adapt to different scenarios. Here's how you can use and work with generic classes in TypeScript.

## Basic Generic Class

To create a generic class, use a type parameter within angle brackets `<>`:

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

In this example, `Box` is a generic class that can hold values of different types (`number` and `string` in this case).

## Multiple Type Parameters

You can use multiple type parameters in a generic class to capture relationships between types:

```typescript
class Pair<T, U> {
  private first: T;
  private second: U;

  constructor(first: T, second: U) {
    this.first = first;
    this.second = second;
  }

  getPair(): [T, U] {
    return [this.first, this.second];
  }
}

let numberStringPair = new Pair<number, string>(42, "forty-two");
let booleanObjectPair = new Pair<boolean, { key: string }>(true, { key: "value" });

console.log(numberStringPair.getPair()); // Output: [42, "forty-two"]
console.log(booleanObjectPair.getPair()); // Output: [true, { key: "value" }]
```

Here, `Pair` is a generic class with two type parameters (`T` and `U`) representing the types of the first and second elements of the pair.

## Generic Constraints in Classes

You can apply constraints to generic types in classes, similar to functions, using the `extends` keyword:

```typescript
interface Lengthy {
  length: number;
}

class Wrapper<T extends Lengthy> {
  private value: T;

  constructor(value: T) {
    this.value = value;
  }

  getLength(): number {
    return this.value.length;
  }
}

let stringWrapper = new Wrapper("Hello");
let arrayWrapper = new Wrapper([1, 2, 3]);

console.log(stringWrapper.getLength()); // Output: 5
console.log(arrayWrapper.getLength());  // Output: 3
```

In this example, `Wrapper` is a generic class that can only be instantiated with types that have a `length` property.

Generic classes provide a powerful way to create reusable and type-safe components in TypeScript. They are commonly used in scenarios where flexibility and type safety are essential.

