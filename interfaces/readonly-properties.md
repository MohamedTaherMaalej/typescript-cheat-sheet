# TypeScript Interfaces: Readonly Properties

In TypeScript interfaces, you can mark properties as `readonly`, indicating that once the object is created, the value of these properties cannot be modified. Readonly properties provide immutability and help ensure the integrity of the object's state. Here's how you can use and work with readonly properties in TypeScript interfaces.

## Declaring Interfaces with Readonly Properties

To declare an interface with readonly properties, use the `readonly` keyword before the property name:

```typescript
interface Point {
  readonly x: number;
  readonly y: number;
}
```

In the above example, both `x` and `y` properties are marked as readonly.

## Implementing Interfaces with Readonly Properties

When implementing an interface with readonly properties, the assigned values cannot be changed after the object is created:

```typescript
let point: Point = { x: 10, y: 20 };

// Error: Cannot assign to 'x' because it is a constant or a read-only property.
point.x = 30;
```

In this example, attempting to modify the value of `x` after the object is created results in a compilation error.

## Readonly Arrays

You can also use `readonly` with arrays to prevent modifications:

```typescript
interface ReadOnlyArrayExample {
  readonly numbers: readonly number[];
}

let readOnlyArrayObject: ReadOnlyArrayExample = {
  numbers: [1, 2, 3]
};

// Error: Index signature in type 'readonly number[]' only permits reading.
readOnlyArrayObject.numbers.push(4);
```

In this example, attempting to push a new element to the `numbers` array results in a compilation error.

## Readonly in Function Parameters

You can use `readonly` in function parameters to ensure that the passed array remains unchanged:

```typescript
function printReadOnlyArray(numbers: readonly number[]) {
  // Implementation
}

let myNumbers: number[] = [1, 2, 3];

printReadOnlyArray(myNumbers);

// Error: Index signature in type 'number[]' only permits reading.
myNumbers.push(4);
```

This ensures that within the `printReadOnlyArray` function, the `numbers` array cannot be modified.

These are basic examples of working with readonly properties in TypeScript interfaces. Explore more advanced features and use cases in the TypeScript documentation as needed.

