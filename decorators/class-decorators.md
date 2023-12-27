# TypeScript Decorators: Class Decorators

Class decorators are a powerful feature in TypeScript that allow you to modify or extend the behavior of a class declaration. They are applied to the constructor of the class and can be used for various purposes, such as adding metadata, logging, or altering class behavior. Here's an introduction to class decorators in TypeScript.

## Creating a Class Decorator

To create a class decorator, you declare a function that takes a constructor function as its target:

```typescript
function myClassDecorator(constructor: Function) {
  // Custom logic can be applied here
  console.log(`Class decorated: ${constructor.name}`);
}

@myClassDecorator
class MyClass {
  // Class implementation
}
```

In this example, the `myClassDecorator` function is a class decorator applied to the `MyClass` class.

## Class Decorator Factory

You can also create a decorator factory, a function that returns a decorator function:

```typescript
function classDecoratorFactory(name: string) {
  return function (constructor: Function) {
    console.log(`Class decorated with name: ${name}`);
  };
}

@classDecoratorFactory("ExampleClass")
class ExampleClass {
  // Class implementation
}
```

Here, `classDecoratorFactory` is a decorator factory that takes a parameter (`name`) and returns a class decorator.

## Class Decorator Execution

Class decorators are executed when the class is declared, not when it's instantiated. They receive the constructor as an argument and can perform actions based on it.

## Practical Example: Logging Class Name

A common use case for class decorators is logging information about the class:

```typescript
function logClassName(constructor: Function) {
  console.log(`Class name: ${constructor.name}`);
}

@logClassName
class LoggableClass {
  // Class implementation
}

// Output: Class name: LoggableClass
```

In this example, the `logClassName` decorator logs the name of the class when it's declared.

## Metadata with Reflect Metadata API

You can use the `Reflect.metadata` API to attach metadata to classes:

```typescript
import "reflect-metadata";

const myMetadataKey = "myMetadata";

function myMetadataDecorator(value: string) {
  return Reflect.metadata(myMetadataKey, value);
}

@myMetadataDecorator("My Custom Metadata")
class ClassWithMetadata {
  // Class implementation
}

const metadataValue = Reflect.getMetadata(myMetadataKey, ClassWithMetadata);
console.log(`Metadata value: ${metadataValue}`);
```

In this example, the `myMetadataDecorator` decorator adds metadata to the class, and `Reflect.getMetadata` retrieves it.

Class decorators provide a way to modify or enhance the behavior of classes in TypeScript. They are a powerful tool for metaprogramming and customizing class functionality.

