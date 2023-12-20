# TypeScript Basic Types: Number

In TypeScript, the `number` type is used to represent numeric values, including integers and floating-point numbers. Here's how you can use and work with numbers in TypeScript.

## Declaring Number Variables

You can declare number variables using the `number` type annotation:

```typescript
let age: number = 25;
let pi: number = 3.14;
```

In the above example, the variables `age` and `pi` are explicitly typed as numbers.

## Basic Arithmetic Operations

Performing basic arithmetic operations with numbers is straightforward:

```typescript
let x: number = 10;
let y: number = 5;

let sum: number = x + y;
let difference: number = x - y;
let product: number = x * y;
let quotient: number = x / y;

console.log(sum);        // Output: 15
console.log(difference); // Output: 5
console.log(product);    // Output: 50
console.log(quotient);   // Output: 2
```

## Increment and Decrement

You can increment and decrement numeric values:

```typescript
let count: number = 0;

count++;
console.log(count); // Output: 1

count--;
console.log(count); // Output: 0
```

## NaN and Infinity

JavaScript/TypeScript has special values for representing "Not-a-Number" (`NaN`) and positive/negative infinity.

```typescript
let result: number = 10 / 0;
console.log(result); // Output: Infinity

let notANumber: number = 0 / 0;
console.log(notANumber); // Output: NaN
```

## Number Methods

Numbers have several built-in methods. Here are a few examples:

```typescript
let absoluteValue: number = Math.abs(-10);
let roundedValue: number = Math.round(3.14);
let randomValue: number = Math.random();

console.log(absoluteValue); // Output: 10
console.log(roundedValue);  // Output: 3
console.log(randomValue);   // Output: Random decimal between 0 and 1
```

These are basic examples of working with numbers in TypeScript. Explore more numeric operations and methods in the TypeScript documentation as needed.

