# TypeScript Modules: Namespaces

In TypeScript, namespaces provide a way to encapsulate code into a named scope, preventing naming conflicts and organizing related functionality. While ES6-style modules are the recommended approach for module organization, namespaces can still be useful in certain scenarios. Here's an introduction to working with namespaces in TypeScript.

## Creating a Namespace

To create a namespace, use the `namespace` keyword:

```typescript
// geometry.ts
namespace Geometry {
  export const PI = 3.141592653589793;
  
  export function calculateCircumference(radius: number): number {
    return 2 * PI * radius;
  }

  export function calculateArea(radius: number): number {
    return PI * radius ** 2;
  }
}
```

In this example, the `Geometry` namespace contains constants and functions related to geometry calculations.

## Accessing Entities in a Namespace

To use entities from a namespace, reference the namespace followed by the entity name:

```typescript
// app.ts
let radius = 5;

let circumference = Geometry.calculateCircumference(radius);
let area = Geometry.calculateArea(radius);

console.log(`Circumference: ${circumference}`);
console.log(`Area: ${area}`);
```

Here, the `calculateCircumference` and `calculateArea` functions from the `Geometry` namespace are accessed in the `app.ts` file.

## Nesting Namespaces

Namespaces can be nested to further organize code:

```typescript
// shapes.ts
namespace Shapes {
  export namespace Circle {
    export function calculateCircumference(radius: number): number {
      return 2 * Geometry.PI * radius;
    }

    export function calculateArea(radius: number): number {
      return Geometry.PI * radius ** 2;
    }
  }

  export namespace Rectangle {
    export function calculatePerimeter(width: number, height: number): number {
      return 2 * (width + height);
    }

    export function calculateArea(width: number, height: number): number {
      return width * height;
    }
  }
}
```

Here, the `Shapes` namespace contains nested namespaces for `Circle` and `Rectangle`.

## Importing and Aliasing Namespaces

To use entities from a namespace in another file, use the `import` statement:

```typescript
// anotherApp.ts
import { Shapes as GeometryShapes } from './shapes';

let circleRadius = 8;
let circleArea = GeometryShapes.Circle.calculateArea(circleRadius);

let rectangleWidth = 5;
let rectangleHeight = 10;
let rectanglePerimeter = GeometryShapes.Rectangle.calculatePerimeter(rectangleWidth, rectangleHeight);
```

In this example, the `Shapes` namespace is imported as `GeometryShapes` in the `anotherApp.ts` file.

While namespaces provide a way to organize code, it's generally recommended to use ES6-style modules for better compatibility and scalability.

