## Статические поля и методы классов

Статические поля и методы принадлежат не какому-то объекту, а всему классу целиком.

```ts
class Person {
    private age: number;
    private name: string;

    static retireAge: number = 65;
    static minAge: number = 0;
    static maxAge: number = 100;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }

    set setAge(age: number) {
        if (age < Person.minAge) {
            console.error("Age is too low");
            return;
        }
        if (age > Person.maxAge) {
            console.error("Age is too high");
            return;
        }
        this.age = age;
    }

    static checkRetirement(age: number): boolean {
        return age >= Person.retireAge;
    }
}
```