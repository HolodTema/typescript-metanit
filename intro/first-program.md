## Первая программа на TypeScript

напишем html где мы подключаем файл app.js

Идея в том, чтобы мы написали файл app.ts, скомпилировали его и в той же папке
получили app.js - и уже app.js будет использоваться в HTML документе и будет 
запускаться в браузере

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Hello world</title>
</head>
<body>
    <h2 id="header"></h2>
    <script src="app.js"></script>
</body>
</html>
```

И напишем app.ts

```ts
class User{
    name : string;
    constructor(_name:string){

        this.name = _name;
    }
}

const tom : User = new User("Том");
const header = document.getElementById("header");
if (header) {
    header.innerHTML = "Привет " + tom.name;
} else {
    console.error("header is null");
}
```

И теперь в терминале скомпилируем

```bash
tsc app.ts
```

И в папке рядом с app.ts появится app.js


