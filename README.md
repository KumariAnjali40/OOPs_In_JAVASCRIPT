                                                               # OOPs_In_JAVASCRIPT

                                                                               

# JavaScript and Classes

```javascript
// ----- JavaScript is a prototype-based language -----

## OOP (Object-Oriented Programming):

### Object:
A collection of properties and methods.

### Why use OOP:

### Parts of OOP:

- Object literal
- Constructor function
- Prototypes
- Classes 
- Instances (new, this)

## 4 Pillars of OOP:

1. **Abstraction:**
   Abstraction involves simplifying complex systems by modeling classes based on the essential properties and behaviors they share. It allows you to focus on the relevant aspects of an object and ignore the irrelevant details.

   ```javascript
   class Car {
       constructor(make, model) {
           this.make = make;
           this.model = model;
       }

       start() {
           console.log(`${this.make} ${this.model} is starting.`);
       }

       drive() {
           console.log(`${this.make} ${this.model} is on the move.`);
       }
   }

   // Usage
   const myCar = new Car('Toyota', 'Camry');
   myCar.start();
   myCar.drive();


2.Encapsulation:
Encapsulation involves bundling data (attributes) and methods (functions) that operate on the data into a single unit, typically a class. It helps in hiding the internal state of an object and only exposing the necessary functionality.

javascript

class BankAccount {
    constructor(balance) {
        this.balance = balance;
    }

    deposit(amount) {
        this.balance += amount;
        console.log(`Deposited ${amount}. New balance: ${this.balance}`);
    }

    withdraw(amount) {
        if (amount <= this.balance) {
            this.balance -= amount;
            console.log(`Withdrawn ${amount}. New balance: ${this.balance}`);
        } else {
            console.log('Insufficient funds.');
        }
    }
}

// Usage
const myAccount = new BankAccount(1000);
myAccount.deposit(500);
myAccount.withdraw(200);
Inheritance:
Inheritance allows a class (subclass/child) to inherit properties and methods from another class (superclass/parent). It promotes code reuse and the creation of a hierarchy of classes.

javascript

// Example: Inheritance with Animal hierarchy
class Animal {
    constructor(name) {
        this.name = name;
    }

    eat() {
        console.log(`${this.name} is eating.`);
    }
}

class Dog extends Animal {
    bark() {
        console.log(`${this.name} is barking.`);
    }
}

// Usage
const myDog = new Dog('Buddy');
myDog.eat();
myDog.bark();
Polymorphism:
Polymorphism allows objects of different types to be treated as objects of a common type. It enables code to work with different types in a uniform way.

javascript

// Example: Polymorphism with a Shape hierarchy
class Shape {
    area() {
        // Default implementation
        return 0;
    }
}

class Circle extends Shape {
    constructor(radius) {
        super();
        this.radius = radius;
    }

    area() {
        return Math.PI * this.radius * this.radius;
    }
}

class Rectangle extends Shape {
    constructor(width, height) {
        super();
        this.width = width;
        this.height = height;
    }

    area() {
        return this.width * this.height;
    }
}

// Usage
const circle = new Circle(5);
const rectangle = new Rectangle(4, 6);

console.log(`Circle Area: ${circle.area()}`);
console.log(`Rectangle Area: ${rectangle.area()}`);
