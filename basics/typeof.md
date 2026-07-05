## Оператор typeof

нужен для проверки типа переменной (аналог is в kotlin)

typeof возвращает строку - тип данных переменной

```ts
let sum: any;
sum = 1200;

if (typeof sum === "number") {
    let result: number = sum / 12;
    console.log(result);
}
else {
    console.log("invalid operation");
}
```

### typeof возвращает следующие строки

```ts
"string"

"number"

"bigint"

"boolean"

"symbol"

"undefined"

"object"

"function"
```
