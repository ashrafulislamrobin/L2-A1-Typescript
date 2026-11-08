# Explain how Access Modifiers (public, private, protected, and readonly) work in TypeScript OOP with examples.

When We were learning classes in TypeScript, we got confused with the words public, private, protected and readonly. At first they looked similar, but they control who can see or change a property.

By default everything is public. That means we can access it from anywhere.

```ts
class Person {
  public name: string;

  constructor(name: string) {
    this.name = name;
  }
}

const p = new Person("Rakib");
console.log(p.name);
```

Private is the opposite. Only the class itself can use that property. Even child classes cannot touch it.

```ts
class Employee {
  private salary: number;

  constructor(salary: number) {
    this.salary = salary;
  }

  getSalary() {
    return this.salary;
  }
}
```

If we try to write `employee.salary` from outside, TypeScript will show an error. That is useful when we want to hide some data.

Protected is a bit in the middle. The class and its child classes can use it, but the outside world cannot.

```ts
class Employee {
  protected name: string;

  constructor(name: string) {
    this.name = name;
  }
}

class Manager extends Employee {
  getName() {
    return this.name; // that will work because of protected
  }
}
```

Readonly is different. It just means the value cannot be changed after it is set. You can still read it from outside if it is public.

```ts
class Product {
  readonly id: number;

  constructor(id: number) {
    this.id = id;
  }
}
```

In the assignment, we used protected for name and private for baseSalary and department. It helped us understand how to control access properly.
