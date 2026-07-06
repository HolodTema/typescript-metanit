## type assertion. Приведение типов в TS

### есть 2 способа

1. через угловые скобки

2. через ключевое слово as

### Через угловые скобки

Например getElementById() возвращает тип HTMLElement|null - но мы хотим привести к типу
HTMLElement. Тогда просто пишем

```ts
const header = <HTMLElement>document.getElementById("header");
header.innerText = "Hello";
```

### Через ключевое слово as

```ts
const header = document.getElementById("header") as HTMLElement;
header.innerText = "Hello";
```
