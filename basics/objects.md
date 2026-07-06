## Объекты в TypeScript

### Тип данных объекта

Переменная, в которую записан объект, получает тип данных этого объекта

```ts
let person = {
    name: "Tom",
    age: 23
};

// or
let person: {name: string, age: number} = {
    name: "Tom",
    age: 23
};
```

То есть мы не можем присвоить другой тип данных

```ts
let person = {
    name: "Tom",
    age: 23
};

// error, invalid data type!
person = {
    name: "Bob";
};

// ok
person = {
    name: "Bob",
    age: 37
};
```

### Необязательные свойства объектов. Знак ?

```ts
let person: {name: string, age?: number};

// теперь свойство age будет необязательным, можно будет не указывать для него
// значение, оно undefined будет если что

person = {
    name: "Tom",
    age: 23
};

console.log(person.age);
// 23

person = {
    name: "Bob";
}

console.log(person.age);
// undefined
```

### Объект как параметр функции

```ts
function printUser(user: {name: string, age: number}) {
    console.log(`name: ${user.name} age: ${user.age}`);
}

const tom = {age: 32, name: "Tom"};
printUser(tom);
```

### При этом объект, который передается в функцию может быть более широким, чем требует функция

```ts
function printUser(user: {name: string, age: number}) {
    console.log(`name: ${user.name} age: ${user.age}`);
}

let bob = {
    name: "Bob",
    age: 30,
    isMarried: true
};

// ok
printUser(bob);
```


