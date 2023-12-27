# TypeScript Decorators: Property Decorators

Property decorators in TypeScript allow you to modify or enhance the behavior of a class property. They are applied to the property descriptor and can be used for various purposes, such as validation, lazy loading, or logging. Here's an introduction to property decorators in TypeScript.

## Creating a Property Decorator

To create a property decorator, you declare a function that takes two parameters: the target object (the prototype) and the property name:

```typescript
function myPropertyDecorator(target: any, propertyName: string) {
  // Custom logic can be applied here
  console.log(`Property decorated: ${propertyName}`);
}

class MyClass {
  @myPropertyDecorator
  myProperty: string;
}
```

In this example, the `myPropertyDecorator` function is a property decorator applied to the `myProperty` property of the `MyClass` class.

## Property Decorator Execution

Property decorators are executed when the class is declared, not when an instance of the class is created. They receive the target object and the property name as arguments.

## Practical Example: Logging Property Changes

A common use case for property decorators is logging information about property changes:

```typescript
function logProperty(target: any, propertyName: string) {
  let value: any;

  Object.defineProperty(target, propertyName, {
    get() {
      return value;
    },
    set(newValue: any) {
      console.log(`Property ${propertyName} changed: ${newValue}`);
      value = newValue;
    },
    enumerable: true,
    configurable: true,
  });
}

class LoggableClass {
  @logProperty
  myProperty: string;
}

const instance = new LoggableClass();
instance.myProperty = "New Value"; // Output: Property myProperty changed: New Value
```

In this example, the `logProperty` decorator modifies the behavior of the `myProperty` property to log a message whenever its value changes.

## Metadata with Reflect Metadata API

You can use the `Reflect.metadata` API to attach metadata to properties:

```typescript
import "reflect-metadata";

const myMetadataKey = "myMetadata";

function myMetadataDecorator(value: string) {
  return Reflect.metadata(myMetadataKey, value);
}

class ClassWithMetadata {
  @myMetadataDecorator("My Custom Metadata")
  myProperty: string;
}

const metadataValue = Reflect.getMetadata(myMetadataKey, ClassWithMetadata.prototype, "myProperty");
console.log(`Metadata value: ${metadataValue}`);
```

In this example, the `myMetadataDecorator` decorator adds metadata to the `myProperty` property, and `Reflect.getMetadata` retrieves it.

Property decorators provide a way to modify or enhance the behavior of properties in TypeScript. They are a powerful tool for metaprogramming and customizing property functionality.


