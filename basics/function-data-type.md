## Функция как тип данных

Каждая функция имеет свой тип данных, как в Kotlin.

```
(параметр1: тип, параметр2: тип,...параметрN: тип) => тип_результата;
```

### Пример

```ts
function hello() {
    console.log("Hello TS!");
}
```

Эта функция имеет тип

```
()=>void;
```

### Использование функции как объекта определенного типа данных

```ts
function hello() {
    console.log("Hello TS!");
}

const fun: ()=>void = hello;
fun();
fun();
```

### Другой пример

```ts
function sum(x: number, y: number): number {
    return x + y;
}

function subtract(x: number, y: number): number {
    return x - y;
}l

function multiply(x: number, y: number): number {
    return x * y;
}

let op: (x: number, y: number)=>number = sum;
console.log(op(5, 3));
//8

op = subtract;
console.log(op(4, 1));
// 3

op = multiply;
console.log(op(3, 3));
// 9
```