Blog 1:Type-Narrowing.md

**Type Narrowing in TypeScript:**

## Introduction:

**TypeScript allows us to use union types, which means a variable can have multiple possible types. However, sometimes we need to perform different operations depending on the actual type of a value. Type narrowing is a technique that helps TypeScript identify a more specific type from a broader type. It makes our code safer and prevents unexpected errors.**

**Detailed Explanation=>

**We can use the typeof operator to check primitive data types such as strings and numbers.**
  
for example:

##function formatValue(value: string | number): string {
  if (typeof value === "string") {
    return value.trim().toLowerCase();
  }

  return value.toFixed(2);
}

**The instanceof operator checks whether an object belongs to a particular class.**
for example:

##class Dog {
  bark(): string {
    return "Woof!";
  }
}

function getSound(animal: Dog | Date): string {
  if (animal instanceof Dog) {
    return animal.bark();
  }

  return animal.toDateString();
}

**The in operator checks whether a particular property exists inside an object. It is useful when working with different object types.**

for example:

##type Admin = { name: string; permissions: string[] };
type Customer = { name: string; purchaseCount: number };

function describe(user: Admin | Customer): string {
  if ("permissions" in user) {
    return `Admin: ${user.name}`;
  }

  return `Customer: ${user.name}`;
}

**Conclusion**:
Type narrowing makes TypeScript code safer and easier to understand. We can use typeof for primitive values, instanceof for class instances, and in for checking object properties. These techniques help developers write reliable and maintainable applications.