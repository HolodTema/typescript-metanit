## Псевдонимы типов в TypeScript

Ключевое слово type

```ts
type id = number|string;

let userId: id = 2;

userId = "idajij";
```

### Другой пример

```ts
type id = number|string;

function printId(inputId: id) {
    console.log(`Id: ${inputId}`);
}

function getId(isNumber: boolean): id {
    if (isNumber) {
        return 1;
    }
    return "1";
}
```

### Еще пример

```ts
type Person = {
    name: string;
    age: number
};

let tom: Person = {
    name: "Tom",
    age: 20
};

let bob: Person = {
    name: "Bob",
    age: 30
};
```

### Расширение псевдонимов

Можно расширять псевдонимы другими псевдонимами через знак амперсанда &

```ts
type Person = {name: string, age: number};
type Employee = Person & {company: string};

function printPerson(person: Person) {
    console.log(`name: ${person.name} age: ${person.age}`);
}

let tom: Person = {name: "Tom", age: 36};
let bob: Employee = {name: "Bob", age: 30, company: "Google"};

printPerson(tom);
printPerson(bob);
```
