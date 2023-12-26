# TypeScript Modules: Basics

In TypeScript, modules provide a way to organize and encapsulate code, preventing naming conflicts and promoting code reusability. TypeScript supports both CommonJS and ES6-style modules. Here's an introduction to working with modules in TypeScript.

## Exporting from a Module

To make a variable, function, or class available outside a module, use the `export` keyword:

```typescript
// math.ts
export const add = (a: number, b: number): number => a + b;

export function multiply(x: number, y: number): number {
  return x * y;
}

export class Calculator {
  static square(x: number): number {
    return x * x;
  }
}
```

In this example, the `add` function, `multiply` function, and `Calculator` class are exported from the `math.ts` module.

## Importing in a Module

To use the exported entities in another module, use the `import` statement:

```typescript
// app.ts
import { add, multiply, Calculator } from './math';

let sum: number = add(3, 5);
let product: number = multiply(2, 4);

let square: number = Calculator.square(3);
```

Here, the `add`, `multiply`, and `Calculator` are imported from the `math` module into the `app.ts` module.

## Default Exports

You can also use default exports for a module:

```typescript
// greetings.ts
const greeting = "Hello, ";

export default greeting;
```

In this example, the `greetings.ts` module exports a single default entity, the `greeting` string.

```typescript
// app.ts
import greeting from './greetings';

console.log(greeting + 'World!'); // Output: Hello, World!
```

When importing a default export, you can choose any name for the imported variable.

## Re-Exporting

Modules can also re-export entities from other modules:

```typescript
// index.ts
export { add, multiply, Calculator } from './math';
export { default as greeting } from './greetings';
```

In this example, the `index.ts` module re-exports entities from both the `math.ts` and `greetings.ts` modules.

These are the basics of working with modules in TypeScript. Modules help organize code and facilitate collaboration in larger projects.
