# Extending Classes

- [What is Inheritance](#what-is-inheritance)

## What is Inheritance

__Inheritance__ is a fundamental concept in Object-Oriented Programming (OOP) that allows a new class to inherit properties and methods from an existing class. It enables the creation of a hierarchy, where a more specialized class, known as the __child class__, can reuse and extend the functionality of a more generalized class, known as the __parent class__.

```js
class Animal {
  constructor(name, sound) {
    this.name = name;
    this.sound = sound;
  }

  makeSound() {
    console.log(this.sound);
  }
}
```
Here, we have a simple `Animal` class with a constructor that initializes the `name` and `sound` properties. Additionally, it has an instance method `makeSound` that logs the sound of the animal.

## Extending the Animal Class

Now, let's create more specialized classes, such as Dog and Cat, that inherit from the Animal class. We can do this by using the `extends` and `super` keywords.

```js
class Dog extends Animal {
  constructor(name, breed) {
    super(name, 'Woof'); // Call the constructor of the parent class
    this.breed = breed;
  }

  wagTail() {
    console.log(`${this.name} is wagging its tail.`);
  }
}
```

In the `Dog` class, we use the `extends` keyword to indicate that it extends the functionality of the `Animal` class. The `super(name, 'Woof')` statement calls the constructor of the parent class (`Animal`), initializing the `name` and setting the default sound to `'Woof'`. The `Dog` class introduces its unique method, `wagTail`.

```js
class Cat extends Animal {
  constructor(name, color) {
    super(name, 'Meow');
    this.color = color;
  }

  purr() {
    console.log(`${this.name} is purring.`);
  }
}
```

Similarly, the `Cat` class extends the `Animal` class. The `super(name, 'Meow')` statement initializes the properties inherited from the parent class. The `Cat` class introduces its unique method, `purr`.

## Child/Parent Relationship

Now, let's discuss the child/parent relationship. When a class extends another class, it inherits its properties and methods. In our example, both `Dog` and `Cat` inherit the `makeSound` method from the Animal class. This relationship allows for code reuse and the creation of a structured class hierarchy.


## Polymorphism in Action
Polymorphism is a key concept in OOP that allows objects of different types to be treated as objects of a common type. In our example, polymorphism is evident through the makeSound method.

```js
const myDog = new Dog('Buddy', 'Golden Retriever');
const myCat = new Cat('Whiskers', 'Gray');

myDog.makeSound(); // Woof
myDog.wagTail(); // Buddy is wagging its tail.

myCat.makeSound(); // Meow
myCat.purr(); // Whiskers is purring.
```
Here, both myDog and myCat have a makeSound method inherited from the Animal class. Although they are instances of different classes (Dog and Cat), we can treat them uniformly by calling the common makeSound method. This demonstrates polymorphism, allowing objects of different types to be used interchangeably.

## Summary
Inheritance using extends and super in JavaScript classes allows for the creation of a hierarchy, where child classes inherit properties and methods from a parent class. This enables the establishment of relationships and the reuse of code. The child/parent relationship is a powerful concept in Object-Oriented Programming, and polymorphism allows for flexibility in treating objects of different types in a uniform manner.