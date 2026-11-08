# What are the core differences between type aliases and interface in TypeScript? When should you choose one over the other?

A type alias is made with the `type` keyword. we can use it for almost anything such as objects, numbers, strings, or even combining different types. For example:

```ts
type Point = {
  x: number;
  y: number;
};

type ID = string | number;
```

An interface is made with the `interface` keyword. It is mainly used for describing the shape of an object. One thing about interfaces is that we can declare the same interface more than once and TypeScript will merge them together.

```ts
interface User {
  name: string;
  age: number;
}

interface User {
  email: string;
}
```

After this, the User interface will have name, age and email.

Interfaces are good when we work with objects and classes, especially if we think the shape might grow later. Types are better when we need unions or more complex combinations.

```ts
type Admin = User & { role: "admin" };
```

If we are describing a simple object shape, both work. But if we need to combine different types or make unions, we prefer using type. For public APIs or things that might be extended, interface feels more natural.

