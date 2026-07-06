## Декомпозиция объектов, которые передаются как параметр функции

Если функция принимает параметром своим объект, то он может автоматически
разложиться на свойства.

```ts
function printUser({name, age}: {name: string, age: number}) {
    console.log(`name: ${name}, age: ${age}`);
}

let tom = {
    name: "Tom",
    age: 33
};

printUser(tom);
```
