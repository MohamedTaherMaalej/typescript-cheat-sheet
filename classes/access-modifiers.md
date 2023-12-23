# TypeScript Classes: Access Modifiers

In TypeScript classes, access modifiers control the visibility of class members, such as properties and methods. There are three main access modifiers: `public`, `private`, and `protected`. Here's how you can use and work with access modifiers in TypeScript classes.

## `public` Access Modifier

The `public` access modifier is the default and allows members to be accessed from anywhere:

```typescript
class Car {
  // Public properties
  public make: string;
  public model: string;

  // Public method
  public startEngine(): void {
    console.log("Engine started!");
  }
}

let myCar = new Car();
myCar.make = "Toyota";
myCar.model = "Camry";
myCar.startEngine();
```

In this example, both properties (`make` and `model`) and the method (`startEngine`) are public and can be accessed from outside the class.

## `private` Access Modifier

The `private` access modifier restricts access to members within the class:

```typescript
class BankAccount {
  private balance: number;

  constructor(initialBalance: number) {
    this.balance = initialBalance;
  }

  private deposit(amount: number): void {
    this.balance += amount;
    console.log(`Deposited ${amount}. New balance: ${this.balance}`);
  }
}

let account = new BankAccount(1000);

// Error: Property 'balance' is private and only accessible within class 'BankAccount'.
console.log(account.balance);

// Error: Property 'deposit' is private and only accessible within class 'BankAccount'.
account.deposit(500);
```

In this example, both the `balance` property and the `deposit` method are private and cannot be accessed from outside the `BankAccount` class.

## `protected` Access Modifier

The `protected` access modifier allows access within the class and its subclasses:

```typescript
class Animal {
  protected sound: string;

  constructor(sound: string) {
    this.sound = sound;
  }

  makeSound(): void {
    console.log(this.sound);
  }
}

class Dog extends Animal {
  bark(): void {
    console.log(`${this.sound} Woof! Woof!`);
  }
}
```

In this example, the `sound` property is protected in the base class (`Animal`), allowing the subclass (`Dog`) to access it.

These are basic examples of working with access modifiers in TypeScript classes. Explore more advanced features and use cases in the TypeScript documentation as needed.

