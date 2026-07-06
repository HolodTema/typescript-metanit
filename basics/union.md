## Объединения типов данных union

Union - это не механизм TS, когда переменная может иметь несколько типов данных 
одновременно - объединение каких-то типов данных.

```ts
let id: number|string = "1345dgg5";

id = 234;

// no errors
```

### Другой пример

```ts
function printId(id: number|string) {
    console.log(`id = ${id}`);
}

let id: string|number = "kdja";
printId(id);

id = 974;
printId(id);
```

### Часто логика различается для разных вариантов типа данных у union-переменной. Поэтому юзают typeof чтобы сделать ветвления

```ts
function printSequence(words: string[]|string) {
    if (typeof words === "string") {
        console.log(words);
    }
    else {
        console.log(words.join(" "));
    }
}

printSequence(["apple", "banana", "plum"]);

printSequence("Hello world");
```
