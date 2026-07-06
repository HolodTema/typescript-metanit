## Оператор in 

Нужен для проверки, что свойство содержится внутри объекта

Возвращает true или false

```ts
function printUser(user: { name: string; age?: number }){
    if("age" in user){
        console.log(`Name: ${user.name} Age: ${user.age}`);
    }
    else{
        console.log(`Name: ${user.name}`);
    }
}
```
