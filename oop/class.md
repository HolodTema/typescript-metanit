## Классы в TypeScript

В TS есть полноценное ООП.

```ts
class User {
    name: string;
    age: number;
}

let tom: User = new User();
tom.name = "Tom";
tom.age = 36;
```

### Можно задать полям класса начальные значения

```ts
class User {
    name: string = "Tom";
    age: number = 18;
}

let user = new User();
console.log(user);
```

### Методы класса и ключевое слово this

```ts
class User {
    name: string;
    age: number;

    print() {
        console.log(`name: ${this.name} age: ${this.age}`);
    }

    toString(): string {
        return `name: ${this.name} age: ${this.age}`;
    }
}

let tom = new User();
tom.name = "Tom";
tom.age = 35;

tom.print();
console.log(tom.toString());
```

### Конструкторы класса

```ts
class User {
    name: string;
    age: number;

    constructor(name: string, age: string) {
        this.name = name;
        this.age = age;
    }

    print() {
        console.log(`name: ${this.name} age: ${this.age}`);
    }
}

let tom = new User("Tom", 35);
tom.print();
```