# TypeScript Functions: Basics

In TypeScript, functions are a fundamental building block of the language, allowing you to define reusable blocks of code. Here's how you can use and work with functions in TypeScript.

## Declaring Functions

To declare a function, use the `function` keyword:

```typescript
function greet(name: string): string {
  return `Hello, ${name}!`;
}
```

In the above example, `greet` is a function that takes a `name` parameter of type `string` and returns a greeting message.

## Function Parameters and Return Types

You can specify parameter types and return types in TypeScript functions:

```typescript
function add(x: number, y: number): number {
  return x + y;
}
```

Here, `add` is a function that takes two parameters (`x` and `y`) of type `number` and returns a value of type `number`.

## Optional Parameters

You can make function parameters optional by using the `?` symbol:

```typescript
function buildName(firstName: string, lastName?: string): string {
  if (lastName) {
    return `${firstName} ${lastName}`;
  } else {
    return firstName;
  }
}
```

In this example, `lastName` is an optional parameter.

## Default Parameter Values

You can provide default values for parameters:

```typescript
function greetUser(name: string = "Guest"): string {
  return `Hello, ${name}!`;
}
```

If no argument is provided for `name`, it defaults to "Guest".

## Rest Parameters

Functions can accept a variable number of arguments using rest parameters:

```typescript
function sum(...numbers: number[]): number {
  return numbers.reduce((total, num) => total + num, 0);
}
```

In this example, the `sum` function can take any number of arguments.

## Arrow Functions

Arrow functions provide a concise syntax for writing functions:

```typescript
const multiply = (x: number, y: number): number => x * y;
```

This is equivalent to the traditional function declaration for `multiply`.

These are basic examples of working with functions in TypeScript. Explore more advanced features and use cases in the TypeScript documentation as needed.

