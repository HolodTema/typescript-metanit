## Модификаторы доступа в TypeScript

Модификаторы доступа применяются к полям и методам класса

### public

public - по умолчанию для полей и методов.

public Поля и методы видны отовсюду

```ts
class Person {
    name: string;
    age: number
}

// is like
class Person {
    public name: string;
    public age: string;
}
```

### private

private поля и методы видны только внутри класса.

И даже в классах-наследниках они не видны.

```ts
class Person {
    private name: string;
    private age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }

    getName(): string {
        return this.name;
    }

    getAge(): number {
        return this.age;
    }
}
```

### protected

protected поля и методы видны только в самом классе и в классах-наследниках.

То есть protected есть смысл задавать, если мы делаем наследование из этого класса.

```ts
class Person {
    protected name: string;
    protected age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }
}

class Employee {
    protected company: string;

    constructor(name: string, age: number, company: string) {
        super(name, age);
        this.company = company;
    }
}
```

### Определение полей класса через его конструктор

Можно заюать модификаторы прямо в параметрах конструктора - и тогда эти
параметры конструктора сразу будут полями.

```ts
class Person {
    constructor(private name: string, private age: number) {
        // do nothing
    }

    getName(): string {
        return this.name;
    }

    getAge(): number {
        return this.age;
    }
}
```

### Определение полей с readonly в конструкторе

Такое поле будет const в классе - его нельзя будет изменить. Или как val в kotlin

```ts
class Person {
    constructor(private readonly name: string, private readonly age: int) {
        // do nothing
    }
}
```
