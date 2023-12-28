# TypeScript Advanced Types: Conditional Types

Conditional types in TypeScript allow you to create types that depend on the values of other types. They enable you to express complex relationships between types based on conditions. Here's an introduction to using conditional types in TypeScript.

## Basics of Conditional Types

Conditional types use the `extends` keyword to create a type that depends on a condition. The syntax is as follows:

```typescript
type MyType<T> = T extends string ? "String Type" : "Non-String Type";

let result1: MyType<string> = "String Type";
let result2: MyType<number> = "Non-String Type";
```

In this example, `MyType` is a conditional type that evaluates whether `T` extends `string`. Depending on the condition, it returns either `"String Type"` or `"Non-String Type"`.

## Using `keyof` with Conditional Types

You can use the `keyof` operator to create conditional types based on object keys:

```typescript
type PropType<T, K extends keyof T> = K extends string ? T[K] : never;

interface Person {
  name: string;
  age: number;
}

let nameValue: PropType<Person, "name"> = "John";
let ageValue: PropType<Person, "age"> = 25;
// let invalidValue: PropType<Person, "address"> = "Invalid"; // Error: Type '"address"' does not exist in type 'keyof Person'.
```

Here, `PropType` is a conditional type that extracts the type of a specific property (`K`) from an object (`T`).

## Distributive Conditional Types

Conditional types are distributive over union types. When used with a union, the type is applied to each member of the union:

```typescript
type BoxedValue<T> = T extends number ? { value: T } : never;

let boxedNumber: BoxedValue<1 | 2 | 3> = { value: 2 };
// let invalidBoxedString: BoxedValue<"a" | "b" | "c"> = { value: "b" }; // Error: Type '"a" | "b" | "c"' does not satisfy the constraint 'number'.
```

In this example, `BoxedValue` is a conditional type that wraps a number in an object if the type is a number.

## Predefined Conditional Types

TypeScript provides several predefined conditional types, including `Exclude`, `Extract`, `NonNullable`, and `ReturnType`. They are commonly used in generic contexts.

```typescript
type Numbers = 1 | 2 | 3 | 4 | 5;
type EvenNumbers = Exclude<Numbers, 1 | 3 | 5>; // 2 | 4
type NonZeroNumbers = NonNullable<Numbers[]>;    // 1 | 2 | 3 | 4 | 5
```

Here, `Exclude` removes specified types from a union, and `NonNullable` removes `null` and `undefined` from a type.

Conditional types provide a powerful way to create flexible and expressive type relationships in TypeScript. They are particularly useful when working with generic types and advanced type scenarios.

