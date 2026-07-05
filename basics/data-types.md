## Типы данных в TypeScript

Есть строгая типизация!

- boolean

- number

- bigint

- string

- Array

- кортежи

- Enum

- Any (произвольный тип, как в kotlin)

- Symbol

- null

- undefined

- Never (аналог Nothing из Kotlin)


### Пример простой

```ts
let x: number = 10;

let hello: string = "Hello";

let isValid: boolean = true;
```

### Как и в kotlin, можно не указывать тип переменной, если он очевиден

```ts
let hello = "Hello";

let n = 15;
```

### Подробнее о number

number - числа. Все числа являются числами с плав. точкой. Даже целые числа - они все
равно как с плав. точкой хранятся.

```ts
let age: number = 36;
let height: number = 1.68;
```

### 8-х-система, 2-х-система и 16-х-система счисления

```ts
let hex: number = 0xf000d;

let oct: number = 0o744;

let bin: number = 0b1010;
```

### Строки string

Могут быть и в двойных, и в одинарных кавычках

```ts
let str1 = "Hello";
let str2 = 'Hello';
```

### Косые кавычки для форматируемых строк

- если нужно добавить переменные в строку

- если нужно сделать многострочную строку

```ts
let firstName = "Tom";
let age = 28;
let info = `Name ${firstName} age ${age}`;
console.log(info);
```

### bigint

bigint - тип данных для больших чисел, больших чем 2**53

```ts
// юзаем конструктор BigInt
const num: bigint = BigInt(100);
console.log(num);

// или юзаем постфикс n
const num: bigint = 100n;
console.log(num);
```

### Если переменная объявляется без определения, она имеет тип Any по умолчанию

```ts
let x;
// x is type of Any

// no errors
x = 10;
x = true;
x = "hello";
```

