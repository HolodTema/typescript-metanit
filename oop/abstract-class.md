## Абстрактные классы в TS

Объекты абстрактных классов нельзя создать

```ts
abstract class Figure {
    getArea() {
        console.log("Not implemented");
    }
}

class Rectangle extends Figure {

    constructor(public width: number, public height: number) {
        super();
    }

    getArea() {
        const square = this.width * this.height;
        console.log("area =", square);
    }
}

// error!
let figure = new Figure();

// ok
let rect = new Rectangle(20, 30);
rect.getArea();
```

### Абстрактные методы

У абстрактных классов можно делать абстрактные методы. Ибо все равно мы не создадим
объект такого класса, а значит и такой метод не вызовем.

```ts
abstract class Figure {

    abstract getArea(): void;

}
```

Если класс наследует абстрактный класс, то он должен реализовать все его абстрактные методы.

### Абстрактные поля

Можно делать и абстрактные поля в абстрактном классе.

Тогда класс-наследник должен реализовать все абстрактные поля своего родительского
абстрактного класса

```ts
abstract class Figure {
    abstract x: nmber;
    abstract y: number;
    abstract getArea(): void;
}

class Rectangle extends Figure {
    constructor(
        public x: number,
        public y: number,
        public width: number,
        public height: number
    ) {
        super();
    }

    getArea(): void {
        const square = this.width * this.height;
        console.log("area =", square);
    }
}
```