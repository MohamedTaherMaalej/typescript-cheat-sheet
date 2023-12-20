# TypeScript Basic Types: Array

In TypeScript, the `array` type is used to represent a collection of elements. Arrays can store values of the same or different types. Here's how you can use and work with arrays in TypeScript.

## Declaring Arrays

You can declare arrays using the desired type followed by square brackets `[]`:

```typescript
let numbers: number[] = [1, 2, 3, 4, 5];
let fruits: string[] = ["apple", "banana", "orange"];
```

Alternatively, you can use the generic `Array` type:

```typescript
let colors: Array<string> = ["red", "green", "blue"];
```

In the above examples, `numbers`, `fruits`, and `colors` are arrays explicitly typed with specific element types.

## Accessing Elements

You can access elements in an array using zero-based indexing:

```typescript
let firstFruit: string = fruits[0];
console.log(firstFruit); // Output: "apple"
```

## Array Methods

Arrays have various built-in methods for manipulation and iteration:

```typescript
let numbers: number[] = [1, 2, 3, 4, 5];

// Adding elements
numbers.push(6);

// Removing elements
numbers.pop();

// Iterating through elements
numbers.forEach((num) => {
  console.log(num);
});

// Finding elements
let foundNumber: number | undefined = numbers.find((num) => num === 3);
console.log(foundNumber); // Output: 3
```

## Multi-dimensional Arrays

Arrays can also be multi-dimensional:

```typescript
let matrix: number[][] = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];

console.log(matrix[1][2]); // Output: 6
```

## Array Destructuring

You can use array destructuring to extract values from an array:

```typescript
let [first, second] = numbers;
console.log(first, second); // Output: 1 2
```

These are basic examples of working with arrays in TypeScript. Explore more array operations and methods in the TypeScript documentation as needed.

