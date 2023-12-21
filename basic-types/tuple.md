# TypeScript Basic Types: Tuple

In TypeScript, a `tuple` is a fixed-size, ordered list of elements. Each element in a tuple can have a different type. Here's how you can use and work with tuples in TypeScript.

## Declaring Tuples

You can declare a tuple by specifying the types of its elements in a specific order:

```typescript
let employee: [number, string, boolean] = [101, "John Doe", true];
```

In the above example, `employee` is a tuple with three elements: a number, a string, and a boolean.

## Accessing Elements

You can access elements in a tuple using zero-based indexing:

```typescript
let employeeID: number = employee[0];
let employeeName: string = employee[1];
let isEmployeeActive: boolean = employee[2];

console.log(employeeID, employeeName, isEmployeeActive);
```

## Modifying Tuples

Tuples are fixed in size, but you can reassign values within the tuple:

```typescript
employee[2] = false;
console.log(employee); // Output: [101, "John Doe", false]
```

## Tuple Destructuring

You can use tuple destructuring to extract values from a tuple into individual variables:

```typescript
let [id, name, isActive] = employee;
console.log(id, name, isActive); // Output: 101 "John Doe" false
```

## Tuple as Function Return Type

Tuples are often used to represent a function that returns multiple values:

```typescript
function getUserInfo(): [number, string] {
  return [1001, "Alice"];
}

let [userID, userName] = getUserInfo();
console.log(userID, userName); // Output: 1001 "Alice"
```

These are basic examples of working with tuples in TypeScript. Explore more tuple operations and use cases in the TypeScript documentation as needed.
