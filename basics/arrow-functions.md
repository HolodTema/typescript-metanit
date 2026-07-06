## Стрелочные функции в TypeScript

```ts
const sum = (x: number, y: number) => {
    return x + y;
}

const result = sum(5, 10);
console.log(result);
// 15
```

### Типы параметров можно опускать

```ts
const sum = (x, y) => {
    return x + y;
}

const result = sum(5, 10);
console.log(result);
// 15
```

### Можно написать стрелочную функцию в одну строчку

```ts
const square = x => x * x;

const hello = () => "Hello world";

console.log(square(3));
// 9

console.log(hello());
// Hello world
```

### Можно передавать стрелочную функцию внутрь функции

```ts
function mathOperation(x: number, y: number, op: (a: number, b: number)=>number): number {
    const result = op(x, y);
    return result;
}

const result1 = mathOperation(1, 1, (x, y)=>x+y);
// 2
```
