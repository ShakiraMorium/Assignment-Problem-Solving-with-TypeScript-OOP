Blog 2: Access-Modifiers.md

# Access Modifiers in TypeScript OOP

Introduction

**Object-Oriented Programming (OOP) helps developers organize programs using classes and objects. TypeScript provides access modifiers to control how class properties and methods can be accessed. The main access modifiers are public, private, and protected. TypeScript also provides readonly, which prevents a property from being reassigned after initialization.**

##Detailed Explanation

**The public modifier allows a property or method to be accessed from anywhere. It is also the default access modifier in TypeScript.**

for example:

## class Student {
  public name: string;

  constructor(name: string) {
    this.name = name;
  }
}

const student = new Student("Mina");
console.log(student.name);


**The private modifier allows access only inside the class where the property is declared. It helps protect sensitive internal class data.**

for example:

## class BankAccount {
  private balance: number = 1000;

  getBalance(): number {
    return this.balance;
  }
}


**The protected modifier allows access inside its own class and its child classes. It is especially useful for inheritance.**

for example:

## class Employee {
  protected name: string = "Alex";
}

class Manager extends Employee {
  getName(): string {
    return this.name;
  }
}


**The readonly modifier prevents a property from being reassigned after initialization. It can be assigned when declared or inside the constructor.**

for example:

## class Product {
  readonly productId: number;

  constructor(id: number) {
    this.productId = id;
  }
}


**Conclution**
Access modifiers help developers control access to class members and implement encapsulation. Use public for accessible members, private for internal details, and protected when subclasses need access. Use readonly when a property should not be reassigned. These features make TypeScript OOP code more organized and maintainable.