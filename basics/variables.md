## Переменные и константы в TS

### var
var - переменная, область видимости на уровне функции. Из-за этого 
может происходить name shadowing - поэтому лучше юзать let.

```ts
var x = "hello";
console.log(x);

// no error
var x = "work";
console.log(x);
```

### let
let - переменная, появилась в ES-2015, область видимости локальная, как в нормальных ЯП.

Рекомендуется юзать вместо var

```ts
let x = "hello";
console.log(x);

// error! cannot initialize it again!
let x = "work";
```

### const

константа, которая не изменится. Область видимость нормальная, локальная

```ts
const x = "HELLO";
```