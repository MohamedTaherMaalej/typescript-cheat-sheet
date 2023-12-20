# TypeScript Basic Types: Boolean

In TypeScript, the `boolean` type is used to represent logical values, either `true` or `false`. Here's how you can use and work with booleans in TypeScript.

## Declaring Boolean Variables

You can declare boolean variables using the `boolean` type annotation:

```typescript
let isLogged: boolean = true;
let hasPermission: boolean = false;
```

In the above example, the variables `isLogged` and `hasPermission` are explicitly typed as booleans.

## Logical Operators

Boolean values can be combined or compared using logical operators:

```typescript
let hasAccess: boolean = isLogged && hasPermission; // Logical AND
let canEdit: boolean = isLogged || hasPermission;    // Logical OR
let cannotDelete: boolean = !hasPermission;          // Logical NOT

console.log(hasAccess);    // Output: false
console.log(canEdit);      // Output: true
console.log(cannotDelete); // Output: true
```

## Comparison Operators

You can compare values using comparison operators, resulting in boolean values:

```typescript
let age: number = 18;

let isAdult: boolean = age >= 18; // Greater than or equal
let isTeenager: boolean = age >= 13 && age < 18; // Compound condition

console.log(isAdult);     // Output: true
console.log(isTeenager);  // Output: false
```

## Truthy and Falsy Values

In JavaScript/TypeScript, certain values are considered "truthy" or "falsy" when used in boolean contexts:

```typescript
let truthyValue: boolean = "Hello"; // Truthy
let falsyValue: boolean = 0;        // Falsy

console.log(!!truthyValue); // Output: true
console.log(!!falsyValue);  // Output: false
```

## Conditional Statements

Boolean values are often used in conditional statements:

```typescript
if (isLogged) {
  console.log("User is logged in.");
} else {
  console.log("User is not logged in.");
}
```

These are basic examples of working with booleans in TypeScript. Explore more boolean operations and use cases in the TypeScript documentation as needed.
