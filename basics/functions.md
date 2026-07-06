## Функции в TypeScript

```ts
function add(a: number, b: number): number {
    return a + b;
}

console.log(add(20, 30));
console.log(add(10, 15));
```

если функция не возвращает ничего, то указывается void или ничего

```ts
function printSum(a: number, b: number): void {
    let result = a + b;
    console.log(result);
}

//или не указываем возвращаемый тип
function printSum(a: number, b: number) {
    let result = a + b;
    console.log(result);
}
```

### Можно не указывать тип возвращаемого значения функции, оно выведется автоматически

```ts
function add(a: number, b: number) {
    return a + b;
}
```

### Необязательные параметры

такие параметры идут после обязательных параметров и отмечаются вопросительным
знаком

```ts
function getName(firstName: string, lastName?: string) {
    if (lastName) {
        return `${firstName} ${lastName}`;
    }
    else {
        return firstName;
    }
}

getName("Ivan");

getName("Ivan", "Serov");
```

### Параметры по умолчанию

```ts
function getName(firstName: string, lastName: string="Ivanov") {
    return firstName + " " + lastName;
}
```

Причем в параметр по умолчанию можно передавать значение не constexpr так скажем

```ts
function defaultLastName(): string {
    return "Smith";
}

function getName(firstName: string, lastName: string=defaultLastName()) {
    return firstName + " " + lastName;
}
```
