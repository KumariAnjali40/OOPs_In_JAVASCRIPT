                                                            # OOPs_In_JAVASCRIPT

                                                                               

# JavaScript and Classes

```javascript
// ----- JavaScript is a prototype-based language -----

## OOP (Object-Oriented Programming):




### Object:
A collection of properties and methods.




### Why use OOP:




### Parts of OOP:

```

- Object literal
- Constructor function
- Prototypes
- Classes 
- Instances (new, this)


```

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






1. Objects:
In JavaScript, an object is a collection of key-value pairs, where the values can be of any data type, including functions. Objects allow you to structure your code in a way that represents real-world entities and their behaviors.


const person = {
    name: 'John',
    age: 30,
    sayHello: function() {
        console.log(`Hello, my name is ${this.name}.`);
    }
};

person.sayHello(); // Output: Hello, my name is John.



Object-Oriented Programming (OOP) is a programming paradigm that uses objects, which are instances of classes, for organizing code. JavaScript is a prototype-based language, which means it doesn't have traditional classes like some other OOP languages. Instead, it uses prototypes for object creation. Here's a comprehensive explanation of OOP concepts in JavaScript:

1. Objects:
In JavaScript, an object is a collection of key-value pairs, where the values can be of any data type, including functions. Objects allow you to structure your code in a way that represents real-world entities and their behaviors.

javascript
Copy code
const person = {
    name: 'John',
    age: 30,
    sayHello: function() {
        console.log(`Hello, my name is ${this.name}.`);
    }
};

person.sayHello(); // Output: Hello, my name is John.


2. Prototype-Based:
JavaScript uses prototype-based inheritance. Every object in JavaScript has a prototype, and it can inherit properties and methods from its prototype. Objects can serve as prototypes for other objects.


// Constructor function
function Person(name, age) {
    this.name = name;
    this.age = age;
}

// Adding a method to the prototype
Person.prototype.sayHello = function() {
    console.log(`Hello, my name is ${this.name}.`);
};

// Creating an instance
const john = new Person('John', 30);
john.sayHello(); // Output: Hello, my name is John.


3. Constructor Functions:
Constructor functions are used to create objects with similar properties and methods. They are invoked using the new keyword, creating instances of the object.


function Car(make, model) {
    this.make = make;
    this.model = model;
}

Car.prototype.start = function() {
    console.log(`${this.make} ${this.model} is starting.`);
};

const myCar = new Car('Toyota', 'Camry');
myCar.start(); // Output: Toyota Camry is starting.


4. Prototypes:
Prototypes in JavaScript allow objects to inherit properties and methods from other objects. Each object has an associated prototype, and when a property or method is accessed on an object, JavaScript looks up the prototype chain.

function Animal(name) {
    this.name = name;
}

Animal.prototype.eat = function() {
    console.log(`${this.name} is eating.`);
};

function Dog(name, breed) {
    Animal.call(this, name);
    this.breed = breed;
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

Dog.prototype.bark = function() {
    console.log(`${this.name} is barking.`);
};

const myDog = new Dog('Buddy', 'Labrador');
myDog.eat();  // Output: Buddy is eating.
myDog.bark(); // Output: Buddy is barking.


5. Classes (ES6+):
ES6 introduced a more syntactic way to define classes in JavaScript. Despite the syntax, it's important to note that JavaScript classes are primarily a syntactical sugar over the existing prototype-based inheritance.

class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    sayHello() {
        console.log(`Hello, my name is ${this.name}.`);
    }
}

const john = new Person('John', 30);
john.sayHello(); // Output: Hello, my name is John.



Static Members:
Definition:
Static members are properties or methods that belong to a class itself, rather than to instances of the class. They are accessed using the class name, not an instance of the class.

Example (Static Method):
javascript
Copy code
class MathOperations {
    static add(x, y) {
        return x + y;
    }
}

// Usage
const result = MathOperations.add(3, 5);
console.log(result); // Output: 8
Example (Static Property):
javascript
Copy code
class Counter {
    static count = 0;

    constructor() {
        Counter.count++;
    }
}

// Usage
const obj1 = new Counter();
console.log(Counter.count); // Output: 1

const obj2 = new Counter();
console.log(Counter.count); // Output: 2



Sure, let's discuss static and private features in the context of JavaScript, specifically in the context of classes.

Static Members:
Definition:
Static members are properties or methods that belong to a class itself, rather than to instances of the class. They are accessed using the class name, not an instance of the class.

Example (Static Method):
javascript
Copy code
class MathOperations {
    static add(x, y) {
        return x + y;
    }
}

// Usage
const result = MathOperations.add(3, 5);
console.log(result); // Output: 8
Example (Static Property):
javascript
Copy code
class Counter {
    static count = 0;

    constructor() {
        Counter.count++;
    }
}

// Usage
const obj1 = new Counter();
console.log(Counter.count); // Output: 1

const obj2 = new Counter();
console.log(Counter.count); // Output: 2
```
Private Members:
Definition:
Private members are properties or methods that are only accessible within the class where they are defined. They cannot be accessed or modified from outside the class.

Example (Private Method):

class Circle {
    #radius;

    constructor(radius) {
        this.#radius = radius;
    }

    #calculateArea() {
        return Math.PI * this.#radius * this.#radius;
    }

    getArea() {
        return this.#calculateArea();
    }
}

// Usage
const myCircle = new Circle(5);
console.log(myCircle.getArea()); // Output: 78.53981633974483
console.log(myCircle.#radius);   // Error: Private field '#radius' is not defined in this context
console.log(myCircle.#calculateArea()); // Error: Private field '#calculateArea' is not defined in this context

```
==================================
⭐ Getter and Setter in Oops
==================================

--In object-oriented programming (OOP), getters and setters are methods used to access and modify the values of private properties of a class. They provide a way to encapsulate the internal state of an object and control access to it.

==================================
⭐ Getter 
==================================

A getter is a method that is used to retrieve the value of a private property. It allows you to access the property as if it were a public property while controlling the access.

====================
```javascript
 class Circle {
    #radius;

    constructor(radius) {
        this.#radius = radius;
    }

    get radius() {
        return this.#radius;
    }
}

// Usage
const myCircle = new Circle(5);
console.log(myCircle.radius); // Output: 5

```


==================================
⭐ Setter
==================================

A setter is a method that is used to modify the value of a private property. It allows you to control the modification of the property and perform additional actions when the property is being set.
====================
```javascript
class Circle {
    #radius;

    constructor(radius) {
        this.#radius = radius;
    }

    get radius() {
        return this.#radius;
    }

    set radius(newRadius) {
        if (newRadius > 0) {
            this.#radius = newRadius;
        } else {
            console.log('Radius must be greater than 0.');
        }
    }
}

// Usage
const myCircle = new Circle(5);
console.log(myCircle.radius); // Output: 5

myCircle.radius = 8;
console.log(myCircle.radius); // Output: 8

myCircle.radius = -3; // Output: Radius must be greater than 0.
console.log(myCircle.radius); // Output: 8 (unchanged)


```



