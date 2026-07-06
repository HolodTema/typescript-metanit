## null и undefined

### параметр компиляции strictNullChecks

по умолчанию этот параметр false - то есть по умолчанию 
мы можем присваивать null и undefined как тип данных

```ts
let a: undefined = undefined;
let b: null = null
```

и мы можем присвоить null и undefined переменным
других типов данных

```ts
let x: number = undefined;

x = null;

x = 5;
```

### Что будет если поставить strictNullChecks = true

```bash
tsc --strictNullChecks main.ts
```

```json
{
    "compilerOptions": {
        "target": "es2015",
        "noImplicitAny": true,
        "noEmitOnError": true,
         
        "strictNullChecks": true,
         
        "outFile": "app.js"
    }
}
```

Тогда будет ошибка при попытке присвоить null или undefined в переменную
другого типа данных.

То есть код ниже выбросит ошибку

```ts
// error
let a: number = null

// error
let n: null = undefined;
```

### Union типов данных вместе с undefined или null

Полезно, когда мы не знаем, дойдет ли до нас значение переменной

```ts
let userId: number|null = null;

function printId(id: number|null) {
    if (id) {
        console.log(`id = ${id}`);
    }
    else {
        console.log("there is no userId");
    }
}

printId(45);
printId(null);
```

### Non-null-assertion operator восклицательный знак !

```ts
const header: HTMLElement|null = document.getElementById("header");

// ошибка, ведь header может быть null
header.innerText = "Hello TS!";
```

Если включен strictNullChecks при компиляции будет ошибка, так как header может быть null.

Можно заюзать оператор ! - разработчик гарантирует, что здесь не будет null ценой возможного NullPointerException в рантайме.

```ts
const header: HTMLElement|null = document.getElementById("header");
header!.innerText = "Hello TS!";
```

## Оператор ! это как оператор !! в Kotlin
