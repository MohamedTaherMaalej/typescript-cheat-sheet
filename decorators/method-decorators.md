# TypeScript Decorators: Method Decorators

Method decorators in TypeScript allow you to modify or enhance the behavior of a class method. They are applied to the property descriptor of the method and can be used for various purposes, such as logging, caching, or validation. Here's an introduction to method decorators in TypeScript.

## Creating a Method Decorator

To create a method decorator, you declare a function that takes three parameters: the target object (the prototype), the method name, and the property descriptor:

```typescript
function myMethodDecorator(target: any, methodName: string, descriptor: PropertyDescriptor) {
  // Custom logic can be applied here
  console.log(`Method decorated: ${methodName}`);
}

class MyClass {
  @myMethodDecorator
  myMethod() {
    // Method implementation
  }
}
```

In this example, the `myMethodDecorator` function is a method decorator applied to the `myMethod` method of the `MyClass` class.

## Method Decorator Execution

Method decorators are executed when the class is declared, not when an instance of the class is created. They receive the target object, the method name, and the property descriptor as arguments.

## Practical Example: Logging Method Calls

A common use case for method decorators is logging information about method calls:

```typescript
function logMethod(target: any, methodName: string, descriptor: PropertyDescriptor) {
  const originalMethod = descriptor.value;

  descriptor.value = function (...args: any[]) {
    console.log(`Method called: ${methodName}`);
    const result = originalMethod.apply(this, args);
    return result;
  };
}

class LoggableClass {
  @logMethod
  myMethod() {
    // Method implementation
  }
}

const instance = new LoggableClass();
instance.myMethod(); // Output: Method called: myMethod
```

In this example, the `logMethod` decorator modifies the behavior of `myMethod` to log a message before and after the original method is called.

## Metadata with Reflect Metadata API

You can use the `Reflect.metadata` API to attach metadata to methods:

```typescript
import "reflect-metadata";

const myMetadataKey = "myMetadata";

function myMetadataDecorator(value: string) {
  return Reflect.metadata(myMetadataKey, value);
}

class ClassWithMetadata {
  @myMetadataDecorator("My Custom Metadata")
  myMethod() {
    // Method implementation
  }
}

const metadataValue = Reflect.getMetadata(myMetadataKey, ClassWithMetadata.prototype, "myMethod");
console.log(`Metadata value: ${metadataValue}`);
```

In this example, the `myMetadataDecorator` decorator adds metadata to the `myMethod` method, and `Reflect.getMetadata` retrieves it.

Method decorators provide a way to modify or enhance the behavior of methods in TypeScript. They are a powerful tool for metaprogramming and customizing method functionality.

