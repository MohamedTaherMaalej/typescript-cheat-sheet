# TypeScript Modules: Module Resolution

Module resolution in TypeScript refers to the process of determining how the compiler locates and loads modules in your project. TypeScript supports various module resolution strategies to handle dependencies and import statements. Here's an overview of module resolution in TypeScript.

## Relative vs. Non-relative Imports

When importing modules, you can use relative or non-relative import paths:

- **Relative Imports:** Start with `./` or `../` to specify the file's relative path.
  ```typescript
  import { myFunction } from './myModule';
  ```

- **Non-relative Imports:** Do not start with `./` or `../`. These are treated as module names and resolved based on module resolution rules.
  ```typescript
  import { someFunction } from 'some-library';
  ```

## Module Resolution Strategies

### 1. Classic

The classic module resolution strategy is used when targeting commonJS or AMD. It looks for `.js`, `.jsx`, `.d.ts`, or `.ts` files and directories. It also uses a `node_modules` folder for third-party libraries.

### 2. Node

Node module resolution is used when targeting commonJS. It includes the Classic strategy but also adds some specific Node.js behavior, like checking for `package.json` files.

### 3. TypeScript

TypeScript module resolution is used when targeting ES6 or System. It is similar to the Node strategy but with some additional checks for TypeScript configuration.

## Module Resolution Configuration

The `tsconfig.json` file can include configuration options for module resolution:

```json
{
  "compilerOptions": {
    "module": "commonJS", // or "AMD", "System", "ES6"
    "moduleResolution": "node", // or "classic" or "typescript"
    // Other compiler options...
  }
}
```

- **module:** Specifies the module system to use.
- **moduleResolution:** Specifies the module resolution strategy.

## Ambient Module Declarations

For non-relative imports of third-party libraries that don't provide TypeScript declarations, you can use ambient module declarations:

```typescript
// typings.d.ts
declare module 'some-library';
```

This tells TypeScript that there is a module named 'some-library' without providing its structure.

Understanding module resolution is crucial for configuring TypeScript projects, especially in complex setups with various dependencies.

