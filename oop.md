# Abstraction

- hides complexity and only shows users relevant information

## Interface

```JS
interface Employee{
    empCode: number;
    empName: string;
    getSalary: (number) => number;
    getManagerName(number) : string;
}
```

The interface includes 2 properties `empCode` and `empName`. Method declaration of `getSalary` using arrow function includes 1 number parameter and a number return type.

The `getManagerName` method is declared using a normal function.

Every object of type Employee must define the two properties and methods.

# Encapsulation

- protect data stored in a class from system-wide access.
- getters and setters

# Polymorphism

- ability to perform a certain action in different ways
- same method name used many times

## Overloading

- same function name - more/less parameters

## Overrding

- same function name - different function from parent class.

# Inheritance

- possible to create a child class that inherits the fields and methods of the parent class.

# What is the difference between ts and js?

- TypeScript is OOP; Javascript is scripting language
- TypeScript has static typing, modules ainterface, and optional parameter function
