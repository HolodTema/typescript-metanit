## Геттеры и сеттеры в TS

В EcmaScript5 в языке TypeScript появлились модификаторы методов get и set
для создания геттеров и сеттеров свойств.

Причем эти геттеры и сеттеры будут работать при обращении к свойству извне каждый раз.

Как в kotlin.

```ts
class Person {
    private name: string;
    private age: number;

    public get age(): number {
        return this.age;
    }

    public get name(): string {
        return this.name;
    }

    public set age(n: number) {
        if (n < || n > 100) {
            console.error("Invalid age");
        }
        else {
            this.age = n;
        }
    }
}

let tom = new Person();
tom.name = "Tom";

// setter worked
tom.age = 36;
// ok

// setter worked
tom.age = -14;
// Invalid age
```


