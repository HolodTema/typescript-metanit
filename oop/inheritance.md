## Наследование в TS

Как в java наследуем один класс от другого через слово extends

```ts
class Person {
    name: string;

    constructor(name: string) {
        this.name = name;
    }

    print() {
        console.log(`Person: name: ${this.name}`);
    }
}

class Employee extends Person {
    company: string;

    work() {
        console.log(`Employee ${this.name} works in ${this.company}`);
    }
}

let bob: Employee = new Employee("Bob");
bob.print();

bob.company = "Oracle";
bob.work();
```

### Переопределение конструктора дочернего класса

Нужно вызвать конструктор родительского класса через super ключевое слово

```ts
class Person {
    name: string;

    constructor(name: string) {
        this.name = name;
    }

    print() {
        console.log(`Person: name: ${this.name}`);
    }
}

class Employee {
    company: string;

    constructor(name: string, company: string) {
        super(name);
        this.company = company;
    }

    work() {
        console.log(`Employee ${this.name} works in ${this.company}`);
    }
}

let bob: Employee = new Employee("Bob");
bob.print();
bob.work();
```