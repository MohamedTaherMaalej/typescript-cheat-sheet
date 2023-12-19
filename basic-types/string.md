# TypeScript Basic Types: String

In TypeScript, the `string` type is used to represent text data. It can include letters, numbers, symbols, or any combination thereof. Here's how you can use and work with strings in TypeScript.

## Declaring String Variables

You can declare string variables using the `string` type annotation:

```typescript
let greeting: string = "Hello, TypeScript!";
```

In the above example, the variable `greeting` is explicitly typed as a string.

## Concatenation

You can concatenate strings using the `+` operator:

```typescript
let firstName: string = "John";
let lastName: string = "Doe";
let fullName: string = firstName + " " + lastName;

console.log(fullName); // Output: John Doe
```

Alternatively, you can use template literals for easier string interpolation:

```typescript
let fullName: string = `${firstName} ${lastName}`;
```

## String Length

You can get the length of a string using the `length` property:

```typescript
let message: string = "TypeScript is awesome!";
let messageLength: number = message.length;

console.log(messageLength); // Output: 22
```

## String Methods

Strings have various built-in methods. Here are some examples:

```typescript
let exampleString: string = "typescript";
let upperCaseString: string = exampleString.toUpperCase();
let lowerCaseString: string = exampleString.toLowerCase();

console.log(upperCaseString); // Output: TYPESCRIPT
console.log(lowerCaseString); // Output: typescript
```

These are just a few basic examples of working with strings in TypeScript. Feel free to explore more string operations and methods in the TypeScript documentation.
